<script lang="ts">
	import Depth3D from '$lib/Depth3D/Base/Depth3D.svelte';
	import { Canvas } from '@threlte/core';

	export let image: {
		image: string;
		depth: string;
	};
</script>

<div class="bg-white">
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
						For your website, made with Svelte, Threlte and Three.js
					</p>
					<div class="mt-10 flex items-center gap-x-6">
						<a href="https://github.com/flo-bit/svelte-depth-3d-component" class="text-sm font-semibold leading-6 text-gray-900"
							>See on Github <span aria-hidden="true">→</span></a
						>
					</div>
				</div>
				<!-- <img
					src="https://images.unsplash.com/photo-1567532900872-f4e906cbf06a?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1280&q=80"
					alt=""
					class="mt-10 aspect-[6/5] w-full max-w-lg rounded-2xl object-cover sm:mt-16 lg:mt-0 lg:max-w-none xl:row-span-2 xl:row-end-2 xl:mt-36"
				/> -->

				<div
					class="mt-10 aspect-[6/5] w-full max-w-lg rounded-2xl overflow-hidden sm:mt-16 lg:mt-0 lg:max-w-none xl:row-span-2 xl:row-end-2 xl:mt-36"
				>
					<Canvas>
						<Depth3D {image} cameraPosition={[0, 0, 7]} />
					</Canvas>
				</div>
			</div>
		</div>
		<div class="absolute inset-x-0 bottom-0 -z-10 h-24 bg-gradient-to-t from-white sm:h-32"></div>
	</div>
</div>
