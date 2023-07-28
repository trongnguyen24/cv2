<script>
	import { ScrollSmoother } from 'gsap/dist/ScrollSmoother';
	import { onMount } from 'svelte';

	// onMount(() => {
	// 	if (ScrollSmoother.get()) {
	// 		let smoother = ScrollSmoother.get();
	// 		smoother.effects().forEach((effect) => effect.kill());
	// 		smoother.effects('[data-lag], [data-speed]');
	// 		ScrollTrigger.refresh();
	// 	}
	// });

	onMount(() => {
		let smoother = ScrollSmoother.get();
		smoother.effects().forEach((effect) => effect.kill());
		smoother.effects('[data-lag], [data-speed]');
	});
</script>
