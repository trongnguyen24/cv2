<script>
	import { gsap } from 'gsap';
	import { ScrollSmoother } from 'gsap/dist/ScrollSmoother';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
	import { onMount } from 'svelte';
	let smoother;

	onMount(() => {
		if (typeof window !== 'undefined') {
			gsap.registerPlugin(ScrollTrigger, ScrollSmoother);
		}

		const ctx = gsap.context(() => {
			smoother = ScrollSmoother.create({
				smooth: 2,
				normalizeScroll: false,
				ignoreMobileResize: false,
				effects: true
			});
		});
		return () => ctx.revert();
	});
</script>
