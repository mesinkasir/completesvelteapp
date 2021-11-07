<script>
    import Navbar from "../widget/Nav.svelte";
	import { quintOut } from 'svelte/easing';
	import { crossfade } from 'svelte/transition';
    import Vodoo from "../widget/fd.svelte";
	import { flip } from 'svelte/animate';

	const [send, receive] = crossfade({
		fallback(node, params) {
			const style = getComputedStyle(node);
			const transform = style.transform === 'none' ? '' : style.transform;

			return {
				duration: 600,
				easing: quintOut,
				css: t => `
					transform: ${transform} scale(${t});
					opacity: ${t}
				`
			};
		}
	});

	let todos = [
		{ id: 1, done: false, description: 'Project A in progress' },
		{ id: 2, done: false, description: 'Start for project B' },
		{ id: 3, done: true, description: 'Development buns project' },
		{ id: 4, done: false, description: 'Turtle Kura Kura Ninja' },
		{ id: 5, done: false, description: 'Super Mario Bross' },
		{ id: 6, done: false, description: 'Development Svelte Project' },
	];

	let uid = todos.length + 1;

	function add(input) {
		const todo = {
			id: uid++,
			done: false,
			description: input.value
		};

		todos = [todo, ...todos];
		input.value = '';
	}

	function remove(todo) {
		todos = todos.filter(t => t !== todo);
	}
</script>
<Navbar/>
<div class='board container'>
<div class='row'>
<div class='col-12 p-3 p-md-5'>
<h1 style="color:#f9cb9c;"><strong>The Agenda</strong></h1>
<p class="lead">Create and save your agenda in here</p>
	<input
		class="new-todo form-control"
		placeholder="input and save project here"
		on:keydown="{event => event.key === 'Enter' && add(event.target)}"
	>
</div>

	<div class='col-12 col-md-6 p-3 p-md-5 card'>
		<h2>Your Agenda</h2>
		{#each todos.filter(t => !t.done) as todo (todo.id)}
			<label
				in:receive="{{key: todo.id}}"
				out:send="{{key: todo.id}}"
				animate:flip
			>
				<input  class="rounded-circle" type=checkbox bind:checked={todo.done}>
				{todo.description}
				<button class="btn btn-danger float-end border border-white" on:click="{() => remove(todo)}">delete</button>
			</label>
		{/each}
	</div>

	<div class='col-12 col-md-6 p-3 p-md-5 card'>
		<h2>Finish</h2>
		{#each todos.filter(t => t.done) as todo (todo.id)}
			<label
				in:receive="{{key: todo.id}}"
				out:send="{{key: todo.id}}"
				animate:flip
			>
				<input class="rounded-circle" type=checkbox bind:checked={todo.done}>
				{todo.description}
				<button class="btn btn-danger float-end btn-sm border border-white" on:click="{() => remove(todo)}">delete</button>
			</label>
		{/each}
	</div>
</div>
</div>
<Vodoo/>