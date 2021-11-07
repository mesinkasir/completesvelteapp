<script>
	import { fade } from 'svelte/transition';
    import Navbar from "../widget/Nav.svelte";
    import Vodoo from "../widget/fd.svelte";
	let product = [
		{ 
			name: 'Coca Cola', 
			qty: '20', 
			img:'https://awsimages.detik.net.id/community/media/visual/2020/05/11/f24a8ad0-38f4-45cd-ad4c-2a5037ae03bb_169.jpeg?w=700&q=90' ,
			cost:'1500' , 
			sell:'5000' , 
			description:'Update on Wednesday' 
		},
		{ name: 'Heniken', qty: '210', img:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR2spYlWoAHRwE3kE0FtCOwsq2R-7144wQvWg&usqp=CAU' , cost:'2500' , sell:'5500' , description:'Last update on saturday' },
		{ name: 'A & W', qty: '50', img:'https://m.media-amazon.com/images/I/510gSpFDHyL.jpg' , cost:'1500' , sell:'5000' , description:'update @ 11/20/2021' },
		{ name: 'Marlboro', qty: '200', img:'https://i.pinimg.com/originals/b9/3b/e4/b93be402723851c4265942c6cb395cb3.jpg' , cost:'1500' , sell:'5500', description:'Out stock 20 Pcs'  }
	];
let jumlah ="stok";
let beli ="Cost";
let jual ="Sell";
	let prefix = '';
	let name = '';
	let qty = '';
	let img = '';
	let cost = '';	
	let sell = '';
	let description = '';
	let i = 0;

	$: filteredProduct = prefix
		? product.filter(stok => {
			const name = `${stok.name}, ${stok.qty}, ${stok.img}, ${stok.cost}, ${stok.sell}, ${stok.description}`;
			return name.toLowerCase().startsWith(prefix.toLowerCase());
		})
		: product;

	$: selected = filteredProduct[i];

	$: reset_inputs(selected);

	function create() {
		product = product.concat({ name, qty, img, cost,sell,description });
		i = product.length - 1;
		name = stok = '';
	}

	function update() {
		selected.name = name;
		selected.qty = qty;
		selected.img = img;
		selected.cost = cost;
		selected.sell = sell;
		selected.description = description;
		product = product;
	}

	function remove() {
		const index = product.indexOf(selected);
		product = [...product.slice(0, index), ...product.slice(index + 1)];

		name = stok = '';
		i = Math.min(i, filteredProduct.length - 2);
	}

	function reset_inputs(stok) {
		name = stok ? stok.name : '';
		qty = stok ? stok.qty : '';
		img = stok ? stok.img : '';
		cost = stok ? stok.cost : '';
		sell = stok ? stok.sell : '';
		description = stok ? stok.description : '';
	}
</script>
<Navbar/>
<div class="container" transition:fade  style="opacity:0.8;">
<div class="row">
<div class="col-12 col-md-12 p-3 p-md-5">	
<h1 style="color:#f9cb9c;">
	<strong>Inventori Managements</strong>
	</h1>
				</div>
<div class="col-12 col-md-4 p-3">	
	<div class="input-group mb-3">
 <span class="input-group-text bg-dark text-white" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">
  <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/>
</svg></span>
<input class="form-control" placeholder="Search Product" bind:value={prefix}>
	</div>
	<hr/>
<select class="form-control" bind:value={i} size={2}>
	{#each filteredProduct as stok, i}
		<option value={i}>
			<div class="card mb-3">
			<img class="card-img-top" src="{stok.img}" alt="{stok.name}"/>
				 <div class="card-body row">
					 <h5 class="card-title text-secondary">{stok.name} </h5>
					 <div class="col-12 text-secondary">{jumlah} : {stok.qty}</div><div class="text-start col-6 text-secondary">{beli} : {stok.cost}</div><div class="text-end col-6 text-secondary">{jual} :{stok.sell}</div><div class="col-12 text-secondary">{stok.description}
			</div>
			</div>
			</div>
	</option>
	{/each}
</select>
			</div>
<div class="col-12 col-md-8 p-3 p-md-5">	
<h1 class="p-3">
	<strong>Inventori</strong>
	</h1>
	<h3 style="color:#f9cb9c;">
		<strong>Input New Data</strong>
	</h3>
<div class="input-group mb-3">
 <span class="input-group-text" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart3" viewBox="0 0 16 16">
  <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .49.598l-1 5a.5.5 0 0 1-.465.401l-9.397.472L4.415 11H13a.5.5 0 0 1 0 1H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM3.102 4l.84 4.479 9.144-.459L13.89 4H3.102zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
</svg></span><input class="form-control" bind:value={name} placeholder="name">
			</div>		
<div class="input-group mb-3">
 <span class="input-group-text" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-box-seam" viewBox="0 0 16 16">
  <path d="M8.186 1.113a.5.5 0 0 0-.372 0L1.846 3.5l2.404.961L10.404 2l-2.218-.887zm3.564 1.426L5.596 5 8 5.961 14.154 3.5l-2.404-.961zm3.25 1.7-6.5 2.6v7.922l6.5-2.6V4.24zM7.5 14.762V6.838L1 4.239v7.923l6.5 2.6zM7.443.184a1.5 1.5 0 0 1 1.114 0l7.129 2.852A.5.5 0 0 1 16 3.5v8.662a1 1 0 0 1-.629.928l-7.185 2.874a.5.5 0 0 1-.372 0L.63 13.09a1 1 0 0 1-.63-.928V3.5a.5.5 0 0 1 .314-.464L7.443.184z"/>
</svg></span>
<input bind:value={qty} class="form-control" placeholder="qty">
</div>
<div class="input-group mb-3">
 <span class="input-group-text" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-image-fill" viewBox="0 0 16 16">
  <path d="M.002 3a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2h-12a2 2 0 0 1-2-2V3zm1 9v1a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V9.5l-3.777-1.947a.5.5 0 0 0-.577.093l-3.71 3.71-2.66-1.772a.5.5 0 0 0-.63.062L1.002 12zm5-6.5a1.5 1.5 0 1 0-3 0 1.5 1.5 0 0 0 3 0z"/>
</svg></span>
<input bind:value={img} class="form-control" placeholder="img">
</div>
<div class="input-group mb-3">
 <span class="input-group-text" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-currency-exchange" viewBox="0 0 16 16">
  <path d="M0 5a5.002 5.002 0 0 0 4.027 4.905 6.46 6.46 0 0 1 .544-2.073C3.695 7.536 3.132 6.864 3 5.91h-.5v-.426h.466V5.05c0-.046 0-.093.004-.135H2.5v-.427h.511C3.236 3.24 4.213 2.5 5.681 2.5c.316 0 .59.031.819.085v.733a3.46 3.46 0 0 0-.815-.082c-.919 0-1.538.466-1.734 1.252h1.917v.427h-1.98c-.003.046-.003.097-.003.147v.422h1.983v.427H3.93c.118.602.468 1.03 1.005 1.229a6.5 6.5 0 0 1 4.97-3.113A5.002 5.002 0 0 0 0 5zm16 5.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0zm-7.75 1.322c.069.835.746 1.485 1.964 1.562V14h.54v-.62c1.259-.086 1.996-.74 1.996-1.69 0-.865-.563-1.31-1.57-1.54l-.426-.1V8.374c.54.06.884.347.966.745h.948c-.07-.804-.779-1.433-1.914-1.502V7h-.54v.629c-1.076.103-1.808.732-1.808 1.622 0 .787.544 1.288 1.45 1.493l.358.085v1.78c-.554-.08-.92-.376-1.003-.787H8.25zm1.96-1.895c-.532-.12-.82-.364-.82-.732 0-.41.311-.719.824-.809v1.54h-.005zm.622 1.044c.645.145.943.38.943.796 0 .474-.37.8-1.02.86v-1.674l.077.018z"/>
</svg></span>
<input bind:value={cost} class="form-control" placeholder="cost">
</div>
<div class="input-group mb-3">
 <span class="input-group-text" id="basic-addon1"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-currency-dollar" viewBox="0 0 16 16">
  <path d="M4 10.781c.148 1.667 1.513 2.85 3.591 3.003V15h1.043v-1.216c2.27-.179 3.678-1.438 3.678-3.3 0-1.59-.947-2.51-2.956-3.028l-.722-.187V3.467c1.122.11 1.879.714 2.07 1.616h1.47c-.166-1.6-1.54-2.748-3.54-2.875V1H7.591v1.233c-1.939.23-3.27 1.472-3.27 3.156 0 1.454.966 2.483 2.661 2.917l.61.162v4.031c-1.149-.17-1.94-.8-2.131-1.718H4zm3.391-3.836c-1.043-.263-1.6-.825-1.6-1.616 0-.944.704-1.641 1.8-1.828v3.495l-.2-.05zm1.591 1.872c1.287.323 1.852.859 1.852 1.769 0 1.097-.826 1.828-2.2 1.939V8.73l.348.086z"/>
</svg></span>
	<input bind:value={sell} class="form-control" placeholder="sell"></div>
<textarea bind:value={description} class="form-control" placeholder="description"></textarea>

<div class='buttons p-3'>
	<button class="btn btn-dark" on:click={create} disabled="{!name || !qty || !img || !cost || !sell || !description}"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-plus-circle" viewBox="0 0 16 16">
  <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
  <path d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"/>
</svg> create</button>
	<button class="btn btn-outline-dark" on:click={update} disabled="{!name || !qty || !img || !cost || !sell || !description ||!selected}"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-check-circle" viewBox="0 0 16 16">
  <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
  <path d="M10.97 4.97a.235.235 0 0 0-.02.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-1.071-1.05z"/>
</svg> update</button>
	<button class="btn btn-danger" on:click={remove} disabled="{!selected}"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-trash" viewBox="0 0 16 16">
  <path d="M5.5 5.5A.5.5 0 0 1 6 6v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5zm2.5 0a.5.5 0 0 1 .5.5v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5zm3 .5a.5.5 0 0 0-1 0v6a.5.5 0 0 0 1 0V6z"/>
  <path fill-rule="evenodd" d="M14.5 3a1 1 0 0 1-1 1H13v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V4h-.5a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1H6a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1h3.5a1 1 0 0 1 1 1v1zM4.118 4 4 4.059V13a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V4.059L11.882 4H4.118zM2.5 3V2h11v1h-11z"/>
</svg> delete</button>
</div>
</div>
</div>
</div>
<Vodoo/>