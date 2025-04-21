<script>
	import { onMount } from 'svelte';
	import '../app.css';
  
	let isDark = false;
  
	onMount(() => {
	  if (typeof document !== 'undefined') {
		document.documentElement.classList.remove('dark');
		isDark = false;
	  }
	});
  
	function toggleDark() {
	  if (typeof document !== 'undefined') {
		isDark = !isDark;
		document.documentElement.classList.toggle('dark', isDark);
	  }
	}
  </script>
  
  
  
  <nav class="sticky top-0 z-50 w-full flex justify-between items-center px-6 py-4 bg-white dark:bg-gray-900 text-black dark:text-white shadow backdrop-blur-sm">
	<div class="text-2xl font-bold">Unreal</div>
  
	<ul class="flex space-x-6">
	  <li><a href="#about" class="hover:underline">About</a></li>
	  <li><a href="#portfolio" class="hover:underline">Portfolio</a></li>
	  <li><a href="#contact" class="hover:underline">Contact</a></li>
	</ul>
  </nav>

  
  <slot />
  
  