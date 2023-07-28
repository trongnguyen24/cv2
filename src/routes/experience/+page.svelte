<script>
	import { gsap, ScrollTrigger, ScrollSmoother } from '$lib/gsap.js';
	import PageGsapRefresh from '$lib/PageGsapRefresh.svelte';
	import { onMount } from 'svelte';

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
	});
</script>

<svelte:head>
	<title>Nguyen Le's Resume - Experience</title>
	<meta name="Nguyen Le's Resume - Experience" content="Nguyen Le's Resume - Experience" />
</svelte:head>

<section class="text-slate-600">
	<h2 class="font-serif text-3xl font-bold text-slate-800 gsapbox2">Experience</h2>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2022-2023 </span>
			<title class="block font-bold text-slate-800">UI/UX Designer</title>
			<p class="mt-2">
				The majority of the work is creating website marketing campaigns, 3D mockup, and small CRUD
				apps using Sveltekit, a JavaScript framework I enjoy.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2021-2022 </span>
			<title class="block font-bold text-slate-800">Designer & Developer</title>
			<p class="mt-2">
				I provided solutions and created the style orientation for a start-up brand, as well as
				producing social media products, and building a website based on WordPress and Haravan.
			</p>
		</div>
	</div>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2013-2021 </span>
			<title class="block font-bold text-slate-800">Graphic Designer</title>
			<p class="mt-2">
				I spent a long period of time working at TPF Vietnam in a variety of positions, including
				graphic designer, high-end retoucher, 3D visualizer, and web designer. I also aid the
				business in resolving the automation issues.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2012-2013 </span>
			<title class="block font-bold text-slate-800">UI/UX - SGVN </title>
			<p class="mt-2">
				Since the concept of UI/UX was rather unfamiliar in Vietnam at that time, I am beginning to
				build websites and apps using Photoshop, which takes ten times longer to complete than the
				existing Figma. I also broaden my understanding of CSS and HTML.
			</p>
		</div>
	</div>

	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox2">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2012</span>
			<title class="block font-bold text-slate-800">Graphic Designer - Golden ACE Viet Nam</title>
			<p class="mt-2">
				I have acquired a wealth of knowledge regarding design methods that utilize CNC machining.
				Additionally, I gained valuable experience in communication design for social media
				platforms.
			</p>
		</div>
	</div>
</section>
