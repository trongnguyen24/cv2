<script>
	import Header from './Header.svelte';
	import '../app.css';
	import Blob from '$lib/blob.svelte';
	import Blob2 from '$lib/blob2.svelte';
</script>

<div class="app relative z-30">
	<Header />
	<h1 class="max-w-3xl mx-auto px-6 text-4xl font-bold text-slate-900">Filters</h1>
	<main class="max-w-3xl mx-auto px-6 py-12">
		<div class="">
			<ul>
				<li>Brightness</li>
				<li>Contrast</li>
				<li>Drop Shadow</li>
			</ul>
		</div>
		<slot />
	</main>
</div>
<div class="fixed top-0 w-screen h-screen overflow-hidden flex justify-between">
	<div id="noiseblob" class="w-full h-full absolute z-20" />
	<Blob2 />
	<Blob />
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
</style>
