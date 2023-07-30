<script>
	// @ts-nocheck

	import { gsap } from '$lib/gsap.js';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';

	onMount(() => {
		gsap.set('.gsapbox2', { opacity: 0, scale: 0.93, y: 15 });
		gsap.to('.gsapbox2', {
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

		const carousels = document.querySelector('.carousels');

		const spanTag = carousels.querySelector('span');

		const spanWidth = spanTag.clientWidth;

		console.log(spanWidth);

		for (let i = 0; i < 5; i++) {
			carousels.appendChild(spanTag.cloneNode(true));
		}

		const movementTimeline = gsap.timeline({
			repeat: -1
		});

		movementTimeline
			.set(carousels, { x: 0 })
			.to(carousels, { x: spanWidth * -1, duration: 5, ease: 'linear' });
	});
</script>

<svelte:head>
	<title>Nguyen Le's Resume - Experience</title>
	<meta name="Nguyen Le's Resume - Experience" content="Nguyen Le's Resume - Experience" />
	<meta property="og:title" content="Nguyen Le's Resume" />
	<meta property="og:type" content="Resume" />
	<meta property="og:image" content={$page.url.origin + '/og-image.jpg'} />
	<meta property="og:url" content={$page.url.origin} />
	<meta
		property="og:description"
		content="I am a skilled UI/UX designer and FE developer based in Ho Chi Minh City"
	/>
</svelte:head>

<section class="text-slate-600">
	<h2
		class="font-serif max-w-[16rem] py-1 border-b border-slate-700 overflow-hidden font-bold text-slate-800 gsapbox2"
	>
		<div class="carousels flex">
			<span class="flex items-center px-2 gap-4"
				><span class="font-sans">·</span>
				EXPERIENCE</span
			>
		</div>
	</h2>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2022-2023 </span>
			<title class="block font-bold text-slate-800">UI/UX Designer - TPF Vietnam</title>
			<p class="mt-2">
				A significant portion of my work here revolves around crafting website marketing campaigns,
				developing 3D mockups, and building small CRUD apps using Sveltekit - a JavaScript framework
				that aligns with my skill set and interests.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2021-2022 </span>
			<title class="block font-bold text-slate-800">Designer & Developer - Coconut Group</title>
			<p class="mt-2">
				I provided effective solutions and defined the style orientation for a startup brand, as
				well as producing social media products, and building a website based on WordPress and
				Haravan.
			</p>
		</div>
	</div>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2013-2021 </span>
			<title class="block font-bold text-slate-800">Graphic Designer - TPF Vietnam</title>
			<p class="mt-2">
				I have a significant tenure at TPF Vietnam, where I held various positions such as graphic
				designer, high-end retoucher, 3D visualizer, and web designer. I also aided the business in
				resolving automation issues to enhance efficicency.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2012-2013 </span>
			<title class="block font-bold text-slate-800">UI/UX - SGVN </title>
			<p class="mt-2">
				Since the concept of UI/UX was rather unfamiliar in Vietnam at that time, I began to build
				websites and apps using Photoshop, which took ten times longer to complete compared to the
				existing Figma. I also broadened my understanding of CSS and HTML.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2012</span>
			<title class="block font-bold text-slate-800">Graphic Designer - Golden ACE Viet Nam</title>
			<p class="mt-2">
				I acquired a wealth of knowledge regarding design methods that utilize CNC machining during.
				Moreover, I gained invaluable experience in communication design for social media platforms.
			</p>
		</div>
	</div>
</section>
