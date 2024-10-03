<script lang="ts">
	import Depth3D from '$lib/Depth3D';

	export let images: {
		image: string;
		depth: string;
	}[];

	let currentImage = 0;
</script>

<div class="relative isolate overflow-hidden min-h-screen w-full">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div
			class="mx-auto max-w-2xl lg:mx-0 lg:grid lg:max-w-none lg:grid-cols-2 lg:gap-x-16 lg:gap-y-6 xl:grid-cols-1 xl:grid-rows-1 xl:gap-x-8"
		>
			<div class="sm:max-w-xl xl:col-end-1 xl:row-start-1 flex flex-col justify-center">
				<div class="mt-20 text-lg leading-8 text-stone-400">
					<h1 class="max-w-2xl text-4xl font-bold tracking-tight text-stone-50 sm:text-6xl mb-8">
						svelte depth based 3d effect
					</h1>
					made with threlte, three.js and tailwind by <a
					href="https://flo-bit.dev"
					target="_blank"
					class="font-semibold text-stone-200"
					>flo-bit</a
				>
				</div>
				<div class="mt-10 flex items-center gap-x-6">
					<a
						href="https://github.com/flo-bit/svelte-depth-3d-component"
						class="text-lg font-semibold leading-6 text-stone-100"
						>get the code <span aria-hidden="true">→</span></a
					>
				</div>
			</div>

			<div class="w-full h-screen flex items-center justify-center">
				{#key images[currentImage]}
				<button on:click={() => {
					currentImage = (currentImage + 1) % images.length;
				}} class="aspect-[2/3] h-full max-h-[80vh] rounded-xl overflow-hidden">
					<Depth3D
						image={{ image: images[currentImage].image, depth: images[currentImage].depth }}
						detail={500}
						cameraPosition={[0, 0, 7]}
					/>
				</button>
				{/key}
			</div>
		</div>
	</div>
</div>
