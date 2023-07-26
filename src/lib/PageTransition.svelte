<script lang="ts">
	import { scale } from 'svelte/transition';
	export let pathname: string = '';
</script>

{#key pathname}
	<div
		class="h-max"
		in:scale={{ duration: 0, delay: 270, opacity: 0, start: 0.94 }}
		out:scale={{ duration: 250, delay: 0, opacity: 0, start: 1.01 }}
	>
		<slot />
	</div>
{/key}
