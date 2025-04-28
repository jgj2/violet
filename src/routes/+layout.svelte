<script lang="ts">
	import '../app.css';
	import Navbar from '$lib/components/ui/navbar/navbar.svelte';
	import {ModeWatcher, mode, toggleMode} from "mode-watcher";

	let { children } = $props();
</script>

<ModeWatcher />
<Navbar />
<main class="place-content-center flex-grow">
	<div class="flex flex-col w-full items-center text-center p-8 md:px-20">
		{@render children()}
	</div>
</main>