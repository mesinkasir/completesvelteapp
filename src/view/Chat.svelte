<script>
	import { fade, fly } from 'svelte/transition';
    import Navbar from "../widget/Nav.svelte";
	import Eliza from 'elizabot';
    import Vodoo from "../widget/fd.svelte";
	import { beforeUpdate, afterUpdate } from 'svelte';

	let div;

	beforeUpdate(() => {
		// determine whether we should auto-scroll
		// once the DOM is updated...
	});

	afterUpdate(() => {
		// ...the DOM is now in sync with the data
	});

	const eliza = new Eliza();

	let comments = [
		{ author: 'eliza', text: eliza.getInitial() }
	];

	function handleKeydown(event) {
		if (event.key === 'Enter') {
			const text = event.target.value;
			if (!text) return;

			comments = comments.concat({
				author: 'user',
				text
			});

			event.target.value = '';

			const reply = eliza.transform(text);

			setTimeout(() => {
				comments = comments.concat({
					author: 'eliza',
					text: '...',
					placeholder: true
				});

				setTimeout(() => {
					comments = comments.filter(comment => !comment.placeholder).concat({
						author: 'eliza',
						text: reply
					});
				}, 500 + Math.random() * 500);
			}, 200 + Math.random() * 200);
		}
	}
</script>
<Navbar/>
<div class="container" style="opacity:0.8;" in:fly="{{ y: 200, duration: 2000 }}" out:fade>

<h1 class="text-center p-3"><strong>Chat With Eliza</strong></h1>
<div class="card p-3 p-md-5">
<div class="row p-3">
<div class="chat col-12 col-md-5 p-3 p-md-5">
<img class="img-fluid" width="300" alt="elizabot" src="https://img.freepik.com/free-vector/contact-us-woman-with-headphones-microphone-with-computer_113065-280.jpg?size=338&ext=jpg"/>

</div>
<div class="col-12 col-md-7 p-3 p-md-5">
<h3 style="color:#f9cb9c;"><strong>Let's Chat with eliza</strong></h3>
	<div class="scrollable " bind:this={div}>
		{#each comments as comment}
			<article class={comment.author}>
				<span>{comment.text}</span>
			</article>
		{/each}
	</div>

	<input class="form-control" on:keydown={handleKeydown}>
	</div>
</div>
</div>
</div>
<Vodoo/>