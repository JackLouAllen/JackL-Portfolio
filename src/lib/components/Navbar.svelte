<script lang="ts">
	const links = [
		{ href: '#about', label: 'About' },
		{ href: '#skills', label: 'Skills' },
		{ href: '#experience', label: 'Experience' },
		{ href: '#education', label: 'Education' },
		{ href: '#projects', label: 'Projects' },
		{ href: '#contact', label: 'Contact' }
	];
</script>

<div class="navbar bg-base-100 shadow-sm px-4 sm:px-8">
	<div class="navbar-start">
		<div class="dropdown">
			<button tabindex="0" class="btn btn-ghost lg:hidden" aria-label="Open menu">
				<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
					<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" />
				</svg>
			</button>
			<ul
				tabindex="0"
				role="menu"
				class="menu menu-sm dropdown-content bg-base-100 rounded-box z-10 mt-3 w-48 p-2 shadow"
			>
				{#each links as link (link.href)}
					<li><a href={link.href}>{link.label}</a></li>
				{/each}
			</ul>
		</div>
		<a href="#top" class="btn btn-ghost text-lg font-semibold">JackLouAllen.info</a>
	</div>
	<div class="navbar-center hidden lg:flex">
		<ul class="menu menu-horizontal px-1">
			{#each links as link (link.href)}
				<li><a href={link.href}>{link.label}</a></li>
			{/each}
		</ul>
	</div>
	<div class="navbar-end">
		<a href="#contact" class="btn btn-primary btn-sm">Get in touch</a>
	</div>
</div>
