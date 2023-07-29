<script>
	// @ts-nocheck

	import { gsap } from '$lib/gsap.js';
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

		const carousels = document.querySelector('.carousels4');

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
	<title>Nguyen Le's Resume - Education</title>
	<meta name="Nguyen Le's Resume - Education" content="Nguyen Le's Resume - Education" />
</svelte:head>

<section class="text-slate-600">
	<h2
		class="font-serif max-w-[16rem] py-1 border-b border-slate-700 overflow-hidden font-bold text-slate-800 gsapbox4"
	>
		<div class="carousels4 flex">
			<span class="flex items-center px-2 gap-4"
				><span class="font-sans">·</span>
				EDUCATION</span
			>
		</div>
	</h2>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox4">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2018 </span>
			<title class="block font-bold text-slate-800">CNTT Nhất Nghệ</title>
			<p class="mt-2">3D Architecture</p>
		</div>
	</div>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox4">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2015 </span>
			<title class="block font-bold text-slate-800">CSC Edu</title>
			<p class="mt-2">PHP & MySQL Basic</p>
		</div>
	</div>
	<div class="grid grid-cols-1 gap-4 mt-6 gsapbox4">
		<div>
			<span class="font-mono text-sm font-semibold text-slate-500">2010-2012 </span>
			<title class="block font-bold text-slate-800">FPT Arena Multimedia</title>
			<p class="mt-2">Graphic Design, Digital Design, Film Making, 3D Visualization</p>
		</div>
	</div>
</section>
