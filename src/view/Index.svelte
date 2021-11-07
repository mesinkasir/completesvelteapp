<script>
    import { Link } from "svelte-routing";
	import { quintOut } from 'svelte/easing';
	import { fade, draw, fly } from 'svelte/transition';
	import { expand } from '../view//custom-transitions.js';
	import { inner, outer } from '../view/Shape.js';

	let visible = true;
</script>
<div class="container">
<div class="row">
<div class="col-12 p-3 p-md-5 text-center">
{#if visible}
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 103 124">
		<g out:fade="{{duration: 200}}" opacity=0.2>
			<path
				in:expand="{{duration: 400, delay: 1000, easing: quintOut}}"
				style="stroke: #ff3e00; fill: #ff3e00; stroke-width: 50;"
				d={outer}
			/>
			<path
				in:draw="{{duration: 1000}}"
				style="stroke:#ff3e00; stroke-width: 1.5"
				d={inner}
			/>
		</g>
	</svg>

	<div class="centered" out:fly="{{y: -20, duration: 800}}">
		{#each 'SVELTE' as char, i}
			<span
				in:fade="{{delay: 1000 + i * 150, duration: 800}}"
			>{char}</span>
		{/each}
	</div>
{/if}


<link href="https://fonts.googleapis.com/css?family=Overpass:100,400" rel="stylesheet">

<style>
	svg {
		width: 50%;
		height: 100%;
	}

	path {
		fill: white;
		opacity: 1;
	}

	label {
		position: absolute;
		top: 1em;
		left: 1em;
	}

	.centered {
		font-size: 20vw;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%,-50%);
		font-family: 'Overpass';
		letter-spacing: 0.12em;
		color: #676778;
		font-weight: 400;
	}

	.centered span {
		will-change: filter;
	}
</style>
</div>
<div class="fixed-bottom">
<div class="p-3 p-md-5 col-12 p-3 text-center">
<Link to="/start" class="btn btn-dark">Get Start Now</Link>
</div>
<div class="p-3 col-12 p-3 text-center">
<p>
<small>
Built with <a href="https://svelte.dev" class="text-dark">svelte</a> host on <a href="https://cloudflare.com" class="text-dark">cloudflare</a> repo on <a href="https://github.com" class="text-dark">github</a>
<br/>support by : <a href="https://hockeycomputindo.com" class="text-dark">hockeycomp</a> - <a href="https://axcora.com" class="text-dark">axcora</a>
<br/>
developer project present <a href="https://creativebydre.com" class="text-dark">creative by dre</a></small>
</p>
</div>
</div>
</div>
</div>
