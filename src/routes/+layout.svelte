<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';
	import Blob from '$lib/blob.svelte';
	import Blob2 from '$lib/blob2.svelte';
	import PageTransition from '$lib/PageTransition.svelte';
	import type { LayoutServerData } from './$types';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import { spring } from 'svelte/motion';

	let coords = spring(
		{ x: -10, y: -10 },
		{
			stiffness: 0.1,
			damping: 0.2
		}
	);
	const onMouseMove = (event: { x: any; y: any }) => {
		$coords = { x: event.x, y: event.y };
	};

	let size = spring(12);

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
			title: 'Skills',
			link: '/skills'
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

	export let data: LayoutServerData;
</script>

<svelte:window
	on:mousemove={onMouseMove}
	on:mousedown={() => size.set(4)}
	on:mouseup={() => size.set(12)}
/>

<div
	class="hidden sm:block"
	id="curs"
	style:--x={`${$coords.x}px`}
	style:--y={`${$coords.y}px`}
	style:width={`${$size}px`}
	style:height={`${$size}px`}
/>

<div class="relative z-30 app">
	<Header />

	<main class="flex flex-col max-w-3xl gap-6 px-6 pt-0 pb-12 mx-auto sm:flex-row">
		<div class=" w-full sm:w-40 shrink-0">
			<ul class="grid flex-wrap grid-cols-2 sm:grid-cols-1 gap-2">
				{#each menu as menu}
					<li
						aria-current={$page.url.pathname === menu.link ? 'true' : undefined}
						class="relative w-full h-6 overflow-hidden transition-colors duration-400 text-slate-600 hover:text-slate-600"
					>
						<a
							aria-current={$page.url.pathname === menu.link ? 'true' : undefined}
							class="absolute top-0 left-0 block transition-all duration-700 aria-current:-translate-y-8"
							href={menu.link}
							>{menu.title}
						</a>
						<a
							aria-current={$page.url.pathname === menu.link ? 'true' : undefined}
							data-sveltekit-noscroll
							class="absolute top-0 left-0 block font-bold transition-all duration-700 translate-y-8 aria-current:-translate-y-0 text-slate-900"
							href={menu.link}
							>{menu.title}
						</a>
					</li>
				{/each}
			</ul>
		</div>
		<div class="w-full">
			<PageTransition pathname={data.pathname}>
				<slot />
			</PageTransition>
		</div>
	</main>
</div>
<div class="fixed top-0 flex justify-between w-screen h-screen overflow-hidden">
	<div id="noiseblob" class="absolute z-20 w-full h-full" />
	<Blob2 />
	<Blob />
</div>

<style>
	/* #noiseblob {
		background-image: url('$lib/images/noise.png');
		animation: noise-animaiton 2.5s steps(3, end) infinite;
		opacity: 1;
	}
 */
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
		/* background-color: black; */
		border: 1px solid #000;
		position: fixed;
		border-radius: 50%;
		pointer-events: none;
		transform: translate(-50%, -50%) translate(var(--x, 0px), var(--y, 0px));
	}
</style>
