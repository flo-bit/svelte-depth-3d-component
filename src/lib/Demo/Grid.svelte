<script lang="ts">
	import { Depth3D } from '$lib/Depth3D';

	export let items: { name: string; image: string; depth: string; href: string }[];
</script>

<div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8">
	<h2 id="products-heading" class="sr-only">Products</h2>

	<div class="grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 xl:gap-x-8">
		{#each items as item}
			<a href={item.href} class="group">
				<div class="w-full overflow-hidden rounded-lg aspect-h-3 aspect-w-2">
					<div class="h-full w-full">
						<Depth3D
							image={{ image: item.image, depth: item.depth }}
							detail={400}
							cameraPosition={[0, 0, 7]}
						/>
					</div>
				</div>
				<div class="mt-4 flex items-center justify-between text-base font-medium text-gray-100">
					<h3>{item.name}</h3>
				</div>
			</a>
		{/each}
	</div>
</div>
