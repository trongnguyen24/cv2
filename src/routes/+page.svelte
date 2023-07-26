<script>
	import { gsap, ScrollTrigger, ScrollSmoother } from '$lib/gsap.js';
	import PageGsapRefresh from '$lib/PageGsapRefresh.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.set('.gsapbox', { opacity: 0, scale: 0.93, y: 15 });
		gsap.to('.gsapbox', {
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
	<title>Nguyen Le's Resume</title>
	<meta name="Nguyen Le's Resume" content="Nguyen Le's Resume" />
</svelte:head>

<section class="text-slate-500">
	<h2 class="font-bold text-3xl text-slate-800 font-serif gsapbox">
		Hi!<br /> I'm <span class=" text-sky-500">Nguyen </span> <br /><span
			class=" font-normal text-xl">User Interface Designer</span
		>
	</h2>
	<p class=" mt-6 gsapbox">
		Based in Ho Chi Minh city, i'm developer and UI/UX designer.<br />
		Hey are looking for designer to build your brand and grow your business? let's shake hands with me.
	</p>
	<div class="grid grid-cols-2 gap-4 mt-6">
		<div class="gsapbox">
			<title class="block text-sky-500 font-semibold text-sm">PHONE</title>+84 0379 573 674
		</div>
		<div class="gsapbox">
			<title class="block text-sky-500 font-semibold text-sm">EMAIL</title>trongnguyen24@gmail.com
		</div>
	</div>
</section>
<PageGsapRefresh />
