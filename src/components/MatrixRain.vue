<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const canvasRef = ref(null)
let animId = null

onMounted(() => {
  const canvas = canvasRef.value
  if (!canvas) return
  const ctx = canvas.getContext('2d')

  let w, h, columns, drops
  const fontSize = 14
  const chars = 'アイウエオカキクケコサシスセソタチツテトナニヌネノハヒフヘホマミムメモヤユヨラリルレロワヲン0123456789ABCDEF<>{}[]=/\\'

  function resize() {
    w = canvas.width = window.innerWidth
    h = canvas.height = window.innerHeight
    columns = Math.floor(w / fontSize)
    drops = Array.from({ length: columns }, () => Math.random() * -100)
  }

  function getAccentColor() {
    const style = getComputedStyle(document.documentElement)
    return style.getPropertyValue('--accent').trim()
  }

  function draw() {
    // Semi-transparent background for trail effect
    const bgColor = getComputedStyle(document.documentElement).getPropertyValue('--bg-primary').trim()
    ctx.fillStyle = bgColor + 'cc'
    ctx.fillRect(0, 0, w, h)

    const accent = getAccentColor()
    ctx.font = `${fontSize}px var(--font-mono, monospace)`

    for (let i = 0; i < columns; i++) {
      const char = chars[Math.floor(Math.random() * chars.length)]
      const x = i * fontSize
      const y = drops[i] * fontSize

      // Lead character is brighter
      ctx.fillStyle = accent
      ctx.globalAlpha = 0.9
      ctx.fillText(char, x, y)

      // Trail characters are dimmer
      if (drops[i] > 0) {
        ctx.globalAlpha = 0.15
        ctx.fillStyle = accent
        const trailChar = chars[Math.floor(Math.random() * chars.length)]
        ctx.fillText(trailChar, x, y - fontSize)
      }

      ctx.globalAlpha = 1

      if (y > h && Math.random() > 0.975) {
        drops[i] = 0
      }
      drops[i] += 0.5
    }

    animId = requestAnimationFrame(draw)
  }

  resize()
  draw()
  window.addEventListener('resize', resize)

  onUnmounted(() => {
    cancelAnimationFrame(animId)
    window.removeEventListener('resize', resize)
  })
})
</script>

<template>
  <canvas ref="canvasRef" class="matrix-canvas"></canvas>
</template>

<style scoped>
.matrix-canvas {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  opacity: 0.12;
  pointer-events: none;
}

[data-theme="light"] .matrix-canvas {
  opacity: 0.06;
}
</style>
