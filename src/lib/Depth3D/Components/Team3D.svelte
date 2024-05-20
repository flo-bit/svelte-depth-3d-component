<script lang="ts">
	import Depth3D from '$lib/Depth3D/Base/Depth3D.svelte';
	import { Canvas } from '@threlte/core';

	export let members: {
		name: string;
		role: string;
		description: string;
		image: string;
		depth: string;
	}[];
</script>

<div class="bg-white py-24 md:py-32">
	<div
		class="mx-auto grid max-w-2xl lg:max-w-4xl grid-cols-1 gap-x-8 gap-y-20 px-6 lg:px-8 xl:grid-cols-5"
	>
		<div class="max-w-2xl xl:col-span-2">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">The Team</h2>
			<p class="mt-6 text-lg leading-8 text-gray-600">
				These are real people with totally not AI generated names and descriptions.
			</p>
		</div>
		<ul role="list" class="-mt-12 space-y-12 divide-y divide-gray-200 xl:col-span-3">
			{#each members as member}
				<li class="flex flex-col gap-10 pt-12 sm:flex-row">
					<!-- <img
					class="aspect-[4/5] w-52 flex-none rounded-2xl object-cover"
					src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80"
					alt=""
				/> -->

					<div class="aspect-[4/5] w-52 flex-none rounded-2xl overflow-hidden">
						<Canvas>
							<Depth3D
								image={{
									image: member.image,
									depth: member.depth
								}}
								cameraPosition={[0, -0.5, 8]}
							/>
						</Canvas>
					</div>
					<div class="max-w-xl flex-auto">
						<h3 class="text-lg font-semibold leading-8 tracking-tight text-gray-900">
							{member.name}
						</h3>
						<p class="text-base leading-7 text-gray-600">{member.role}</p>
						<p class="mt-6 text-base leading-7 text-gray-600">
							{member.description}
						</p>
						<ul role="list" class="mt-6 flex gap-x-6">
							<li>
								<a href="https://twitter.com/flobit_dev" class="text-gray-400 hover:text-gray-500">
									<span class="sr-only">X</span>
									<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20" aria-hidden="true">
										<path
											d="M11.4678 8.77491L17.2961 2H15.915L10.8543 7.88256L6.81232 2H2.15039L8.26263 10.8955L2.15039 18H3.53159L8.87581 11.7878L13.1444 18H17.8063L11.4675 8.77491H11.4678ZM9.57608 10.9738L8.95678 10.0881L4.02925 3.03974H6.15068L10.1273 8.72795L10.7466 9.61374L15.9156 17.0075H13.7942L9.57608 10.9742V10.9738Z"
										/>
									</svg>
								</a>
							</li>
							<li>
								<a
									href="https://linkedin.com/in/floriankillius"
									class="text-gray-400 hover:text-gray-500"
								>
									<span class="sr-only">LinkedIn</span>
									<svg class="h-5 w-5" fill="currentColor" viewBox="0 0 20 20" aria-hidden="true">
										<path
											fill-rule="evenodd"
											d="M16.338 16.338H13.67V12.16c0-.995-.017-2.277-1.387-2.277-1.39 0-1.601 1.086-1.601 2.207v4.248H8.014v-8.59h2.559v1.174h.037c.356-.675 1.227-1.387 2.526-1.387 2.703 0 3.203 1.778 3.203 4.092v4.711zM5.005 6.575a1.548 1.548 0 11-.003-3.096 1.548 1.548 0 01.003 3.096zm-1.337 9.763H6.34v-8.59H3.667v8.59zM17.668 1H2.328C1.595 1 1 1.581 1 2.298v15.403C1 18.418 1.595 19 2.328 19h15.34c.734 0 1.332-.582 1.332-1.299V2.298C19 1.581 18.402 1 17.668 1z"
											clip-rule="evenodd"
										/>
									</svg>
								</a>
							</li>
						</ul>
					</div>
				</li>
			{/each}
		</ul>
	</div>
</div>
