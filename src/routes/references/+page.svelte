<script>
	// @ts-nocheck

	import { gsap } from '$lib/gsap.js';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.set('.gsapbox5', { opacity: 0, scale: 0.93, y: 15 });
		gsap.to('.gsapbox5', {
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

		const carousels = document.querySelector('.carousels5');

		const spanTag = carousels.querySelector('span');

		const spanWidth = spanTag.clientWidth;

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
	<title>Nguyen Le's Resume - References</title>
	<meta name="Nguyen Le's Resume - References" content="Nguyen Le's Resume - References" />
</svelte:head>

<section class="text-slate-600">
	<h2
		class="font-serif max-w-[16rem] w-full py-1 border-b border-slate-700 overflow-hidden font-bold text-slate-800 gsapbox5"
	>
		<div class="carousels5 flex">
			<span class="flex items-center px-2 gap-4"
				><span class="font-sans">·</span>
				REFERENCES</span
			>
		</div>
	</h2>
	<ul class="grid grid-cols-1 gi gap-6 my-6">
		<li class="gsapbox5 flex flex-col">
			<title class="block text-slate-500 text-xs">MANAGER · TPF Vietnam</title><span
				class="font-semibold text-slate-900 mt-1">Mr. Nhan Dong</span
			>

			<span class="block font-mono text-sm">P: <a href="tel:0908567834">0908 567 834</a></span>
			<span class="block font-mono text-sm"
				>M: <a href="mailto:wookofu@gmail.com">wookofu@gmail.com</a></span
			>
		</li>
		<li class="gsapbox5 flex flex-col">
			<title class="block text-slate-500 text-xs">CO-FOUNDER · Coconut Group</title><span
				class="font-semibold text-slate-900 mt-1">Mr. Cuong Viet</span
			>

			<span class="block font-mono text-sm">P: <a href="tel:0989116656">0989 116 656</a></span>
			<span class="block font-mono text-sm"
				>M: <a href="mailto:vietcuong308@gmail.com">vietcuong308@gmail.com</a></span
			>
		</li>
	</ul>
</section>
