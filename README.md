# svelte depth 3d component

Display an image with a fake 3D effect, using a depth map. Made for svelte, using threlte, threejs and tailwindcss. Still a work in progress, but usable.

[Try the demo here.](https://flo-bit.github.io/svelte-depth-3d-component/)



https://github.com/user-attachments/assets/74b05fd6-feef-49da-9b38-523b65bf5da8



## How to use

1. Copy and paste the [`src/lib/Depth3D/`](https://download-directory.github.io/?url=https%3A%2F%2Fgithub.com%2Fflo-bit%2Fsvelte-depth-3d-component%2Ftree%2Fmain%2Fsrc%2Flib%2FDepth3D) folder of this repository into your svelte projects `src/lib/` folder.
2. Install [tailwindcss](https://tailwindcss.com/docs/guides/sveltekit) and [threlte (core and extras)](https://threlte.xyz/docs/learn/getting-started/installation) (work through their setup or see below for commands)
3. Get an image and generate a accompanying depth map, for example using [zoedepth](https://replicate.com/cjwbw/zoedepth)
4. Use the `Depth3D` component in your pages directly like so:

```svelte
<script>
  // Depth3D example
  import Depth3D from '$lib/Depth3D';
</script>

<!-- will adjust to the parents size/position -->
<Depth3D
	image={{
		image: 'your-image.png',
		depth: 'your-depth.png'
	}}
/>
```

## Which images work well

This effect only simulates 3D, so some images will show weird artifacts. Portraits with a single person in the middle tend to work well. The effect will also depend on the quality of the depth map. Some trial and error might be necessary to get the desired effect.

## Installing the dependencies

### TailwindCSS (assuming you created your svelte app with the svelte create command)

1. Install
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
2. Update your tailwind.config.js file to find files with tailwind classes:
```js
content: ['./src/**/*.{html,js,svelte,ts}'],
```
3. Create a app.css file in your src folder.
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
4. Import the css file in your +layout.svelte file
```svelte
<script>
  import "../app.css";
</script>

<slot />
```

### Threlte (core and extras)

1. Install
```bash
npm install three @threlte/core \
            @threlte/extras \
            @types/three
```
