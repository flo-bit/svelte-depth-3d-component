<script>
	import Grid from './Grid.svelte';
	import Hero from './Hero.svelte';
	import Quote from './Quote.svelte';

	let url = '/svelte-depth-3d-component';
</script>

<a class="absolute top-4 right-4" href="https://github.com/flo-bit/svelte-depth-3d-component">
	<svg fill="currentColor" viewBox="0 0 24 24" aria-hidden="true" class="w-8 h-8">
		<path
			fill-rule="evenodd"
			d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
			clip-rule="evenodd"
		/>
	</svg>
</a>

<Hero
	images={[
		{
			image: url + '/images/girl.jpg',
			depth: url + '/images/girl-depth.png'
		},
		{
			image: url + '/images/napoleon-crossing-the-alps.jpg',
			depth: url + '/images/napoleon-crossing-the-alps-depth.png'
		},
		{
			image: url + '/images/van-gogh-self-portrait.webp',
			depth: url + '/images/van-gogh-self-portrait-depth.png'
		},
		{
			image: url + '/images/mona-lisa.jpg',
			depth: url + '/images/mona-lisa-depth.png'
		}
	]}
/>

<Quote
	image={{
		image: url + '/images/albert_einstein.png',
		depth: url + '/images/albert_einstein-depth.png'
	}}
/>

<Grid
	items={[
		{
			name: 'Napoleon Crossing the Alps',
			image: url + '/images/napoleon-crossing-the-alps.jpg',
			depth: url + '/images/napoleon-crossing-the-alps-depth.png',
			href: '#'
		},
		{
			name: 'Van Gogh Self Portrait',
			image: url + '/images/van-gogh-self-portrait.webp',
			depth: url + '/images/van-gogh-self-portrait-depth.png',
			href: '#'
		},
		{
			name: 'Mona Lisa',
			image: url + '/images/mona-lisa.jpg',
			depth: url + '/images/mona-lisa-depth.png',
			href: '#'
		}
	]}
/>
