<script lang="ts">
	import Depth3D from '$lib/Depth3D';

	export let image: {
		image: string;
		depth: string;
	};
</script>

<section class="isolate overflow-hidden px-6 lg:px-8">
	<div class="relative mx-auto max-w-2xl py-24 sm:py-32 lg:max-w-4xl">
		<figure class="grid grid-cols-1 items-center gap-x-6 gap-y-8 lg:gap-x-10">
			<div class="relative col-span-2 lg:col-start-1 lg:row-start-2">
				<blockquote class="text-xl font-semibold leading-8 text-stone-50 sm:text-2xl sm:leading-9">
					<p>
						"I love this component, it's so easy to use and looks amazing on my website."
					</p>
				</blockquote>
			</div>
			<div class="col-end-1 w-32 lg:row-span-4 lg:w-72 h-32 lg:h-72 relative">
				<div class="absolute inset-0">
					<Depth3D {image} rounded />
				</div>
			</div>
			<figcaption class="text-base lg:col-start-1 lg:row-start-3">
				<div class="font-semibold text-stone-100">Albert Einstein</div>
				<div class="mt-1 text-stone-400">Famous person</div>
			</figcaption>
		</figure>
	</div>
</section>
