<script>
	import { gsap, ScrollTrigger, ScrollSmoother } from '$lib/gsap.js';
	import PageGsapRefresh from '$lib/PageGsapRefresh.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		gsap.set('.gsapbox3', { opacity: 0, scale: 0.93, y: 15 });
		gsap.to('.gsapbox3', {
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
	});
</script>

<svelte:head>
	<title>Nguyen Le's Resume -Tools of choice</title>
	<meta
		name="Nguyen Le's Resume - Tools of choice"
		content="Nguyen Le's Resume - Tools of choice"
	/>
</svelte:head>

<section class="text-slate-600">
	<h2 class="font-bold text-3xl text-slate-800 font-serif gsapbox3">Tools of choice</h2>
	<div class="flex w-full gap-4 mt-6 gsapbox3">
		<div class="w-full">
			<h3 class="block text-slate-800 font-bold">UI/UX Tools</h3>
			<ul class="gap-4 mt-2 grid grid-cols-3">
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
			</ul>
		</div>
	</div>

	<div class="flex w-full gap-4 mt-6 gsapbox3">
		<div class="w-full">
			<h3 class="block text-slate-800 font-bold">3D Tools</h3>
			<ul class="gap-4 mt-2 grid grid-cols-3">
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
			</ul>
		</div>
	</div>

	<div class="flex w-full gap-4 mt-6 gsapbox3">
		<div class="w-full">
			<h3 class="block text-slate-800 font-bold">Development</h3>
			<ul class="gap-4 mt-2 grid grid-cols-3">
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
				<li class="flex gap-2 items-center">
					<svg
						width="24"
						height="24"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M8 24C10.208 24 12 22.208 12 20V16H8C5.792 16 4 17.792 4 20C4 22.208 5.792 24 8 24Z"
							fill="#0ACF83"
						/>
						<path d="M4 12C4 9.792 5.792 8 8 8H12V16H8C5.792 16 4 14.208 4 12Z" fill="#A259FF" />
						<path d="M4 4C4 1.792 5.792 0 8 0H12V8H8C5.792 8 4 6.208 4 4Z" fill="#F24E1E" />
						<path d="M12 0H16C18.208 0 20 1.792 20 4C20 6.208 18.208 8 16 8H12V0Z" fill="#FF7262" />
						<path
							d="M20 12C20 14.208 18.208 16 16 16C13.792 16 12 14.208 12 12C12 9.792 13.792 8 16 8C18.208 8 20 9.792 20 12Z"
							fill="#1ABCFE"
						/>
					</svg>

					Figma
				</li>
			</ul>
		</div>
	</div>
</section>
