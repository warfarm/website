<script>
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import '../app.css';

	let isDark = false;
	let mounted = false;

	onMount(() => {
		if (browser) {
			isDark = false;
			document.documentElement.classList.remove('dark');
			mounted = true;
		}
	});

	function toggleDark() {
		isDark = !isDark;
		document.documentElement.classList.toggle('dark', isDark);
	}
</script>

{#if mounted}
	<button
		on:click={toggleDark}
		class="fixed top-4 right-4 px-4 py-2 rounded bg-gray-200 dark:bg-gray-800 text-black dark:text-white transition z-50"
	>
		Toggle {isDark ? 'Light' : 'Dark'} Mode
	</button>

	<slot />
{/if}
