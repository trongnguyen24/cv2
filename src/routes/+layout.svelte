<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';
	import Blob from '$lib/blob.svelte';
	import Blob2 from '$lib/blob2.svelte';
	import PageTransition from '$lib/PageTransition.svelte';
	import type { LayoutServerData } from './$types';
	import { ScrollSmoother } from '$lib/gsap.js';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import { spring } from 'svelte/motion';

	let coords = spring(
		{ x: 50, y: 50 },
		{
			stiffness: 0.1,
			damping: 0.25
		}
	);
	const onMouseMove = (event: { x: any; y: any }) => {
		$coords = { x: event.x, y: event.y };
	};

	let size = spring(10);

	let menu = [
		{
			title: 'Bio',
			link: '/'
		},
		{
			title: 'Experience',
			link: '/experience'
		},
		{
			title: 'Tools of choice',
			link: '/tools-of-choice'
		},
		{
			title: 'Education',
			link: '/education'
		},
		{
			title: 'References',
			link: '/references'
		}
	];

	onMount(() => {
		ScrollSmoother.create({
			smooth: 1.2, // how long (in seconds) it takes to "catch up" to the native scroll position
			effects: true, // looks for data-speed and data-lag attributes on elements
			smoothTouch: 0.1 // much shorter smoothing time on touch devices (default is NO smoothing on touch devices)
		});
	});

	export let data: LayoutServerData;
</script>

<svelte:window
	on:mousemove={onMouseMove}
	on:mousedown={() => size.set(4)}
	on:mouseup={() => size.set(10)}
/>

<div
	class="hidden sm:block"
	id="curs"
	style:--x={`${$coords.x}px`}
	style:--y={`${$coords.y}px`}
	style:width={`${$size}px`}
	style:height={`${$size}px`}
/>

<div id="smooth-wrapper">
	<div class="app relative z-30">
		<div id="smooth-content">
			<Header />

			<main class="max-w-3xl mx-auto px-6 py-12 flex flex-col gap-6 md:flex-row">
				<div class="w-40 shrink-0">
					<ul class="flex flex-col gap-2">
						{#each menu as menu}
							<li
								aria-current={$page.url.pathname === menu.link ? 'true' : undefined}
								class="font-semibold text-slate-400 hover:text-slate-600 transition-colors duration-300 aria-current:text-slate-900"
							>
								<a data-sveltekit-noscroll class="block" href={menu.link}>{menu.title}</a>
							</li>
						{/each}
					</ul>
				</div>
				<div class="flex-1">
					<PageTransition pathname={data.pathname}>
						<slot />
					</PageTransition>
				</div>
			</main>
		</div>
	</div>
	<div class="fixed top-0 w-screen h-screen overflow-hidden flex justify-between">
		<div id="noiseblob" class="w-full h-full absolute z-20" />
		<Blob2 />
		<Blob />
	</div>
</div>

<style>
	#noiseblob {
		background-image: url('$lib/images/noise.png');
		animation: noise-animaiton 2.5s steps(3, end) infinite;
		opacity: 1;
	}
	@keyframes noise-animaiton {
		0% {
			background-position: 10px;
		}
		20% {
			background-position: 50px;
		}
		40% {
			background-position: 0px;
		}
		60% {
			background-position: 150px;
		}
		80% {
			background-position: 220px;
		}
		100% {
			background-position: 110px;
		}
	}

	#curs {
		width: 10px;
		height: 10px;
		z-index: 50;
		background-color: black;
		position: fixed;
		border-radius: 50%;
		pointer-events: none;
		transform: translate(-50%, -50%) translate(var(--x, 0px), var(--y, 0px));
	}
</style>
