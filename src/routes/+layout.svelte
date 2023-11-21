<script>
	import '../app.css';
	import Navbar from '../lib/navbar.svelte';
	import Header from '../lib/header.svelte';

	import { onMount, afterUpdate } from 'svelte';

	onMount(() => {
		waveAnimation.beginElement();
	});

	afterUpdate(() => {
		if (waveAnimation) {
			waveAnimation.beginElement();
		}
	});
</script>

<main class="bg-rich-black w-screen h-screen overflow-hidden">
	<div class="bg-[url('/line.svg')] bg-no-repeat bg-center w-screen h-screen animate-unblur">
		<Header />
		<slot />
		<Navbar />
	</div>
</main>
