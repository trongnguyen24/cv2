<script>
	import { gsap, ScrollTrigger, ScrollSmoother } from '$lib/gsap.js';
	import PageGsapRefresh from '$lib/PageGsapRefresh.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.set('.gsapbox4', { opacity: 0, scale: 0.93, y: 15 });
		gsap.to('.gsapbox4', {
			y: 0,
			opacity: 1,
			scale: 1,
			duration: 0.5,
			stagger: {
				// wrap advanced options in an object
				each: 0.2,
				from: 'start',
				grid: 'auto'
			}
		});
	});
</script>

<svelte:head>
	<title>Nguyen Le's Resume - Experience</title>
	<meta name="Nguyen Le's Resume - Experience" content="Nguyen Le's Resume - Experience" />
</svelte:head>

<section class="text-slate-600">
	<h2 class="font-bold text-3xl text-slate-800 font-serif gsapbox4">Education</h2>
</section>
