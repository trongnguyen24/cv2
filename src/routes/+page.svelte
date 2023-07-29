<script>
	// @ts-nocheck

	import { gsap } from '$lib/gsap.js';
	import { onMount } from 'svelte';
	import avatar_avif from '$lib/images/nl.avif';
	import avatar_webp from '$lib/images/nl.webp';
	import avatar_jpg from '$lib/images/nl.jpg';

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

		const carousels = document.querySelector('.carousels1');

		const spanTag = carousels.querySelector('.job');

		const spanWidth = spanTag.clientWidth;

		for (let i = 0; i < 5; i++) {
			carousels.appendChild(spanTag.cloneNode(true));
		}

		const movementTimeline = gsap.timeline({
			repeat: -1
		});

		movementTimeline
			.set(carousels, { x: 0 })
			.to(carousels, { x: spanWidth * -1, duration: 9, ease: 'linear' });
	});
</script>

<svelte:head>
	<title>Nguyen Le's Resume</title>
	<meta name="Nguyen Le's Resume" content="Nguyen Le's Resume" />
</svelte:head>

<section class="text-slate-700">
	<div class="flex flex-row gap-6">
		<picture
			class=" w-[6.5rem] rounded-3xl outline-2 outline outline-slate-500 rounded-br-none overflow-hidden gsapbox"
		>
			<source srcset={avatar_webp} type="image/webp" />
			<img src={avatar_jpg} alt="Welcome" />
		</picture>
		<h2 class="font-bold text-3xl text-slate-800 font-serif gsapbox">
			Hi!<br /> I'm <span class=" text-blue-500">Nguyen </span> <br />
			<div
				class="font-serif text-base max-w-[11rem] bg-blue-500 mt-2 rounded-full rounded-bl-none border-blue-500 overflow-hidden font-bold text-slate-800"
			>
				<div class="carousels1 flex">
					<span class="flex items-center font-mono text-white gap-3 shrink-0 job"
						><span>UI/UX Designer</span> · <span>3D Visual</span> · <span>Developer</span>
						<span>·</span>
					</span>
				</div>
			</div>
		</h2>
	</div>
	<p class=" mt-6 gsapbox">
		Based in Ho Chi Minh city, i'm developer and UI/UX designer.<br />
		Hey are looking for designer to build your brand and grow your business? let's shake hands with me.
	</p>
	<div class="grid md:grid-cols-2 gap-4 mt-6">
		<div class="gsapbox">
			<title class="block text-slate-500 text-xs">PHONE</title>+84 0379 573 674
		</div>
		<div class="gsapbox">
			<title class="block text-slate-500 text-xs">EMAIL</title>trongnguyen24@gmail.com
		</div>
	</div>
</section>
