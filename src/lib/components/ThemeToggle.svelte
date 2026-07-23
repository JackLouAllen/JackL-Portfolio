<script lang="ts">
	import { onMount } from 'svelte';

	type Theme = 'latte' | 'macchiato';

	let theme = $state<Theme>('latte');

	onMount(() => {
		theme = (document.documentElement.getAttribute('data-theme') as Theme) ?? 'latte';
	});

	function toggle() {
		theme = theme === 'macchiato' ? 'latte' : 'macchiato';
		document.documentElement.setAttribute('data-theme', theme);
		localStorage.setItem('theme', theme);
	}
</script>

<button
	class="btn btn-ghost btn-circle swap swap-rotate"
	class:swap-active={theme === 'macchiato'}
	onclick={toggle}
	aria-label="Toggle light/dark theme"
>
	<svg class="swap-off h-5 w-5 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
		<path
			d="M5.64 17l-.71.71a1 1 0 101.41 1.41l.71-.71A1 1 0 005.64 17zM5 12a1 1 0 00-1-1H3a1 1 0 000 2h1a1 1 0 001-1zm7-7a1 1 0 001-1V3a1 1 0 10-2 0v1a1 1 0 001 1zm3.66-.83l-.71-.71a1 1 0 10-1.41 1.41l.71.71a1 1 0 001.41-1.41zM6.34 6.34L5.63 5.63A1 1 0 004.22 7l.71.71a1 1 0 001.41-1.41zM12 6a6 6 0 106 6 6 6 0 00-6-6zm7 5h-1a1 1 0 100 2h1a1 1 0 100-2zm-1.05 6.95a1 1 0 00-1.41 1.41l.71.71a1 1 0 001.41-1.41zM12 19a1 1 0 00-1 1v1a1 1 0 102 0v-1a1 1 0 00-1-1z"
		/>
	</svg>
	<svg class="swap-on h-5 w-5 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
		<path
			d="M21.64 13a1 1 0 00-1.05-.14 8.05 8.05 0 01-3.37.73 8.15 8.15 0 01-8.14-8.1 8.59 8.59 0 01.25-2A1 1 0 008 2.36a10.14 10.14 0 1014 11.69 1 1 0 00-.36-1.05z"
		/>
	</svg>
</button>
