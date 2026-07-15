<script setup>
const projects = [
	{
		name: "NFCQC",
		description: "Manufacuring Managemtnt System",
		tech: ["Vue", "MySQL", "Laravel", "Typescript"],
		featured: true,
		private: true,
	},
  {
		name: "Sirius",
		description: "Online English Instituition Management System",
		tech: ["Vue", "SQLite", "Laravel", "Typescript"],
		featured: true,
		private: true,
	},
	{
		name: "laraduct",
		description:
			"Browse, buy & sell products. Simple. Fast. Done. — A full-featured e-commerce marketplace built with Laravel.",
		tech: ["Laravel", "PHP", "MySQL"],
		url: "https://github.com/MuhammadFarouk12/laraduct",
		featured: true,
		private: false,
	},
	{
		name: "nodejs_students_users_api",
		description:
			"RESTful API for users and students with role-based CRUD operations and JWT authentication.",
		tech: ["Node.js", "Express", "JWT", "MongoDB"],
		url: "https://github.com/MuhammadFarouk12/nodejs_students_users_api",
		featured: true,
		private: false,
	},
	{
		name: "AI_Content_Recommendation",
		description:
			"A content recommendation engine using Case-Based Reasoning, suggesting content based on user preferences.",
		tech: ["Python", "AI/ML", "CBR"],
		url: "https://github.com/MuhammadFarouk12/AI_Content_Recommendation",
		featured: false,
		private: false,
	},
	{
		name: "Dynamic_Porfolio",
		description:
			"A dynamic portfolio website built with TypeScript for showcasing projects and skills.",
		tech: ["TypeScript", "HTML", "CSS"],
		url: "https://github.com/MuhammadFarouk12/Dynamic_Porfolio",
		featured: false,
		private: false,
	},
	{
		name: "pixel-positions",
		description:
			"A Laravel-based web application for job postings and recruitment management.",
		tech: ["Laravel", "PHP", "MySQL"],
		url: "https://github.com/MuhammadFarouk12/pixel-positions",
		featured: false,
		private: false,
	},
	{
		name: "Home-Ecommerce-Page",
		description:
			"A responsive e-commerce landing page built with SCSS for a clean, modern aesthetic.",
		tech: ["HTML", "SCSS", "CSS"],
		url: "https://github.com/MuhammadFarouk12/Home-Ecommerce-Page",
		featured: false,
		private: false,
	},
	{
		name: "prayingApi",
		description:
			"A simple app to get prayer times by city and country using the Aladhan API.",
		tech: ["JavaScript", "API"],
		url: "https://github.com/MuhammadFarouk12/prayingApi",
		featured: false,
		private: false,
	},
];

const featuredProjects = projects.filter(p => p.featured);
const otherProjects = projects.filter(p => !p.featured);
</script>

<template>
	<section id="projects" class="section">
		<div class="container">
			<span class="section-label">Projects</span>
			<h2 class="section-title">Featured Work</h2>

			<!-- Featured Projects -->
			<div class="featured-grid">
				<component
					v-for="(project, i) in featuredProjects"
					:key="project.name"
					:is="project.private ? 'div' : 'a'"
					v-bind="
						project.private
							? {}
							: { href: project.url, target: '_blank', rel: 'noopener' }
					"
					:class="['featured-card', 'fade-in']"
					:style="{ animationDelay: `${i * 0.1}s` }"
				>
					<div class="featured-top">
						<svg
							class="project-icon"
							width="20"
							height="20"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
						>
							<path
								d="M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z"
							/>
						</svg>
						<svg
							v-if="!project.private"
							class="external-icon"
							width="16"
							height="16"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
						>
							<path
								d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
							/>
							<polyline points="15 3 21 3 21 9" />
							<line x1="10" y1="14" x2="21" y2="3" />
						</svg>
						<span v-else class="private-badge">
							<svg
								width="14"
								height="14"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							>
								<rect x="3" y="11" width="18" height="11" rx="2" ry="2" />
								<path d="M7 11V7a5 5 0 0 1 10 0v4" />
							</svg>
							Private
						</span>
					</div>
					<h3 class="featured-name">{{ project.name }}</h3>
					<p class="featured-desc">{{ project.description }}</p>
					<div class="featured-tech">
						<span v-for="t in project.tech" :key="t" class="tag">{{ t }}</span>
					</div>
				</component>
			</div>

			<!-- Other Projects -->
			<h3 class="other-title">Other Projects</h3>
			<div class="other-grid">
				<component
					v-for="project in otherProjects"
					:key="project.name"
					:is="project.private ? 'div' : 'a'"
					v-bind="
						project.private
							? {}
							: { href: project.url, target: '_blank', rel: 'noopener' }
					"
					class="other-card"
				>
					<div class="other-top">
						<svg
							width="18"
							height="18"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
						>
							<path
								d="M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z"
							/>
						</svg>
						<svg
							v-if="!project.private"
							class="external-icon"
							width="14"
							height="14"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
						>
							<path
								d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
							/>
							<polyline points="15 3 21 3 21 9" />
							<line x1="10" y1="14" x2="21" y2="3" />
						</svg>
						<span v-else class="private-badge">
							<svg
								width="12"
								height="12"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							>
								<rect x="3" y="11" width="18" height="11" rx="2" ry="2" />
								<path d="M7 11V7a5 5 0 0 1 10 0v4" />
							</svg>
							Private
						</span>
					</div>
					<h4 class="other-name">{{ project.name }}</h4>
					<p class="other-desc">{{ project.description }}</p>
					<div class="other-tech">
						<span v-for="t in project.tech" :key="t" class="tag">{{ t }}</span>
					</div>
				</component>
			</div>
		</div>
	</section>
</template>

<style scoped>
.featured-grid {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	gap: 20px;
	margin-bottom: 56px;
}

.featured-card {
	display: flex;
	flex-direction: column;
	padding: 28px;
	background: var(--bg-card);
	border: 1px solid var(--border-color);
	border-radius: 12px;
	text-decoration: none;
	transition:
		border-color 0.2s,
		box-shadow 0.2s,
		transform 0.2s;
}

.featured-card:hover {
	border-color: var(--accent-border);
	box-shadow: 0 0 24px var(--accent-glow);
	transform: translateY(-2px);
}

.featured-top {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 24px;
}

.project-icon {
	color: var(--accent);
}

.external-icon {
	color: var(--text-secondary);
	transition: color 0.2s;
}

.featured-card:hover .external-icon {
	color: var(--accent);
}

.featured-name {
	font-family: var(--font-mono);
	font-size: 18px;
	font-weight: 600;
	color: var(--text-heading);
	margin-bottom: 12px;
}

.featured-desc {
	font-size: 14px;
	color: var(--text-secondary);
	line-height: 1.7;
	margin-bottom: 20px;
	flex-grow: 1;
}

.featured-tech {
	display: flex;
	flex-wrap: wrap;
	gap: 8px;
}

.other-title {
	font-family: var(--font-mono);
	font-size: 18px;
	font-weight: 600;
	color: var(--text-heading);
	margin-bottom: 20px;
}

.other-grid {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	gap: 16px;
}

.other-card {
	padding: 24px;
	background: var(--bg-card);
	border: 1px solid var(--border-color);
	border-radius: 10px;
	text-decoration: none;
	transition:
		border-color 0.2s,
		box-shadow 0.2s;
}

.other-card:hover {
	border-color: var(--accent-border);
	box-shadow: 0 0 16px var(--accent-glow);
}

.other-top {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 16px;
	color: var(--text-secondary);
}

.other-card:hover .other-top {
	color: var(--accent);
}

.other-name {
	font-family: var(--font-mono);
	font-size: 15px;
	font-weight: 600;
	color: var(--text-heading);
	margin-bottom: 8px;
}

.other-desc {
	font-size: 13px;
	color: var(--text-secondary);
	line-height: 1.6;
	margin-bottom: 16px;
}

.other-tech {
	display: flex;
	flex-wrap: wrap;
	gap: 6px;
}

.other-tech .tag {
	font-size: 11px;
	padding: 3px 8px;
}

@media (max-width: 1024px) {
	.featured-grid,
	.other-grid {
		grid-template-columns: repeat(2, 1fr);
	}
}

@media (max-width: 640px) {
	.featured-grid,
	.other-grid {
		grid-template-columns: 1fr;
	}
}
</style>
