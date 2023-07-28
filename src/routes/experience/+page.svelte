<script>
	// @ts-nocheck

	import { gsap } from '$lib/gsap.js';
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
</svelte:head>

<section class="text-slate-600">
	<h2
		class="font-serif max-w-xs w-full py-2 border rounded-full border-slate-700 overflow-hidden text-3xl font-bold text-slate-800 gsapbox2"
	>
		<div class="carousels flex">
			<span class="flex items-center px-4 gap-8"
				><svg
					width="24"
					height="24"
					viewBox="0 0 24 24"
					fill="none"
					class="stroke-current"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M11.4802 3.49897C11.5224 3.3958 11.5945 3.30755 11.6871 3.24543C11.7797 3.18331 11.8886 3.15015 12.0002 3.15015C12.1117 3.15015 12.2206 3.18331 12.3132 3.24543C12.4058 3.30755 12.4779 3.3958 12.5202 3.49897L14.6452 8.60997C14.6849 8.70561 14.7503 8.78841 14.8341 8.84928C14.9179 8.91015 15.0169 8.94672 15.1202 8.95497L20.6382 9.39697C21.1372 9.43697 21.3392 10.06 20.9592 10.385L16.7551 13.987C16.6766 14.0542 16.6181 14.1417 16.586 14.2399C16.5539 14.3382 16.5494 14.4434 16.5732 14.544L17.8582 19.929C17.884 20.037 17.8772 20.1503 17.8387 20.2545C17.8002 20.3587 17.7317 20.4491 17.6418 20.5144C17.5519 20.5797 17.4447 20.6168 17.3337 20.6212C17.2227 20.6256 17.1129 20.597 17.0182 20.539L12.2932 17.654C12.2049 17.6002 12.1035 17.5717 12.0002 17.5717C11.8968 17.5717 11.7954 17.6002 11.7072 17.654L6.98215 20.54C6.88741 20.598 6.7776 20.6266 6.66661 20.6222C6.55561 20.6178 6.4484 20.5807 6.35852 20.5154C6.26864 20.4501 6.20011 20.3597 6.1616 20.2555C6.12309 20.1513 6.11632 20.038 6.14215 19.93L7.42715 14.544C7.45098 14.4434 7.4466 14.3381 7.41449 14.2399C7.38238 14.1416 7.32379 14.0541 7.24515 13.987L3.04115 10.385C2.95696 10.3126 2.89606 10.2169 2.8661 10.11C2.83614 10.0031 2.83846 9.88971 2.87277 9.78412C2.90707 9.67852 2.97184 9.58543 3.05892 9.51654C3.14599 9.44766 3.25149 9.40606 3.36215 9.39697L8.88015 8.95497C8.9834 8.94672 9.08237 8.91015 9.16618 8.84928C9.24998 8.78841 9.31537 8.70561 9.35515 8.60997L11.4802 3.49897Z"
						stroke-width="1.5"
						stroke-linecap="round"
						stroke-linejoin="round"
					/>
				</svg>
				Experience</span
			>
		</div>
	</h2>
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
