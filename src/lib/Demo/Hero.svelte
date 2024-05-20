<script lang="ts">
	import Depth3D from '$lib/Depth3D';

	export let image: {
		image: string;
		depth: string;
	};
</script>

<div class="relative isolate overflow-hidden pt-14">
	<div class="mx-auto max-w-7xl px-6 py-32 sm:py-40 lg:px-8">
		<div
			class="mx-auto max-w-2xl lg:mx-0 lg:grid lg:max-w-none lg:grid-cols-2 lg:gap-x-16 lg:gap-y-6 xl:grid-cols-1 xl:grid-rows-1 xl:gap-x-8"
		>
			<h1
				class="max-w-2xl text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl lg:col-span-2 xl:col-auto"
			>
				Depth based 3D effect
			</h1>
			<div class="mt-6 max-w-xl lg:mt-0 xl:col-end-1 xl:row-start-1">
				<p class="text-lg leading-8 text-gray-600">
					For your svelte website, made with Threlte, Three.js and TailwindCSS
				</p>
				<div class="mt-10 flex items-center gap-x-6">
					<a href='https://github.com/flo-bit/svelte-depth-3d-component' class="text-sm font-semibold leading-6 text-gray-900"
						>Get the code <span aria-hidden="true">→</span></a
					>
				</div>
			</div>

			<div
				class="mt-10 aspect-[6/5] w-full max-w-lg rounded-2xl overflow-hidden sm:mt-16 lg:mt-0 lg:max-w-none xl:row-span-2 xl:row-end-2 xl:mt-36"
			>
				<Depth3D {image} cameraPosition={[0, 0, 7]} />
			</div>
		</div>
	</div>
</div>
