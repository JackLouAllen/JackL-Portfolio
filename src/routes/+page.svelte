<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';

	const skills: string[] = [];

	const experience: { role: string; company: string; period: string; description: string }[] = [];

	const education: { degree: string; school: string; period: string }[] = [];

	const projects: { title: string; description: string; href: string }[] = [];
</script>

<div id="top">
	<Navbar />

	<section class="hero min-h-[70vh] bg-base-200">
		<div class="hero-content text-center">
			<div class="max-w-xl">
				<h1 class="text-5xl font-bold">Hi, I'm Jack LouAllen</h1>
				<a href="#projects" class="btn btn-primary mt-6">View my work</a>
			</div>
		</div>
	</section>

	<section id="about" class="px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">About</h2>
			<p class="mt-4 text-base-content/80"></p>
		</div>
	</section>

	<section id="skills" class="bg-base-200 px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">Skills</h2>
			<div class="mt-6 flex flex-wrap gap-2">
				{#each skills as skill (skill)}
					<span class="badge badge-outline badge-lg">{skill}</span>
				{/each}
			</div>
		</div>
	</section>

	<section id="experience" class="px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">Experience</h2>
			<ul class="mt-6 space-y-8">
				{#each experience as job (job.role + job.company)}
					<li>
						<div class="flex items-baseline justify-between gap-4">
							<h3 class="text-lg font-semibold">{job.role} · {job.company}</h3>
							<span class="text-sm text-base-content/60">{job.period}</span>
						</div>
						<p class="mt-2 text-base-content/80">{job.description}</p>
					</li>
				{/each}
			</ul>
		</div>
	</section>

	<section id="education" class="bg-base-200 px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">Education</h2>
			<ul class="mt-6 space-y-6">
				{#each education as item (item.degree + item.school)}
					<li class="flex items-baseline justify-between gap-4">
						<div>
							<h3 class="text-lg font-semibold">{item.degree}</h3>
							<p class="text-base-content/80">{item.school}</p>
						</div>
						<span class="text-sm text-base-content/60">{item.period}</span>
					</li>
				{/each}
			</ul>
		</div>
	</section>

	<section id="projects" class="px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">Projects</h2>
			<div class="mt-8 grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
				{#each projects as project (project.title)}
					<div class="card bg-base-100 shadow-sm">
						<div class="card-body">
							<h3 class="card-title">{project.title}</h3>
							<p>{project.description}</p>
							<div class="card-actions justify-end">
								<a href={project.href} class="btn btn-sm btn-outline">View</a>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<section id="contact" class="bg-base-200 px-4 py-16">
		<div class="mx-auto max-w-5xl">
			<h2 class="text-3xl font-bold">Contact</h2>
			<p class="mt-4 text-base-content/80"></p>
		</div>
	</section>

	<footer class="footer footer-center p-6 text-base-content/60">
		<p>&copy; {new Date().getFullYear()} JackLouAllen.info. All rights reserved.</p>
	</footer>
</div>
