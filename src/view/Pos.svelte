<script>
    import { fade, fly } from 'svelte/transition';
    import Navbar from "../widget/Nav.svelte";
    import Vodoo from "../widget/fd.svelte";
	let count = 0;
	let chicken ="chicken"; 
	let chickenimage ='https://thumbs.dreamstime.com/b/southern-fried-chicken-french-fries-portions-cardboard-scoop-white-background-107649032.jpg';
	function chickenPrice() {
		count += 35000;
	}
	let cola = "coca cola";	
	let colaimage ='https://cdn.idntimes.com/content-images/community/2021/03/p14-michel-konbini-a-20180211-b383504511d4cd14b25273d672b4d0cc-27f280b8caf5944a7033055ffbd48773.jpg';
	function colaPrice() {
		count += 15000;
	}
	let frice = "french fries";	
	let friceimage ='https://img.freepik.com/free-vector/french-fries-box-template_383392-247.jpg?size=626&ext=jpg';
	function fricePrice() {
		count += 15500;
	}
	let burger = "burger";	
	let burgerimage ='https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ3b5V78c57FietH-ysGcMLy158Q9m82907WmgeDcifW6Q1dkNoPC0XqKnEVJ56CjnnYMk&usqp=CAU';
	function burgerPrice() {
		count += 45500;
	}
	let beer = "beer";	
	let beerimage ='https://assets.sainsburys-groceries.co.uk/gol/7985395/1/640x640.jpg';
	function beerPrice() {
		count += 85500;
	}
	let steak = "steak";	
	let steakimage ='https://asset.kompas.com/crops/ydaGTqPZ1D5MvuEXhWBSZ0cAuuI=/0x0:1000x667/750x500/data/photo/2020/08/02/5f264273cb0d7.jpg';
	function steakPrice() {
		count += 185500;
	}
	
	$: total = count;
	</script>
<Navbar/>
<div class="container" in:fly="{{ y: 400, duration: 2000 }}">
	<div class="row"  style="opacity:0.8;">
	<div class="col-12 p-3 p-md-5">	
		<h3 class="text-center" style="color:#f9cb9c;"><strong>
			Resto Ku</strong>
		</h3>
<div class="row">
<button class="col-6 col-md-3 p-1 card"  on:click={chickenPrice}>
			<img class="img-fluid" alt="{chicken}" src="{chickenimage}"/>
	<p>
		{chicken}</p> 
		</button>
<button class="col-6 col-md-3 p-1 card" on:click={burgerPrice}>
	<img class="img-fluid" alt="{burger}" src="{burgerimage}"/>
	<p>{burger}</p>
		</button>
<button class="col-6 col-md-3 p-1 card" on:click={steakPrice}>
	<img class="img-fluid" alt="{steak}" src="{steakimage}"/>
	<p>{steak}</p>
		</button>
<button class="col-6 col-md-3 p-1 card" on:click={colaPrice}>
	<img class="img-fluid" alt="{cola}" src="{colaimage}"/>
	<p>{cola}</p>
		</button>
<button class="col-6 col-md-3 p-1 card" on:click={fricePrice}>
	<img class="img-fluid" alt="{frice}" src="{friceimage}"/>
	<p>{frice}</p>
		</button>
<button class="col-6 col-md-3 p-1 card" on:click={beerPrice}>
	<img class="img-fluid" alt="{beer}" src="{beerimage}"/>
	<p>{beer}</p>
		</button>
	</div>
	</div>
	<div class="p-5"></div>
	<div class="col-12 p-3 fixed-bottom">	
	<h3 class="bg-danger rounded p-3 text-center text-white"><strong>
	Total : $.{count}
		</strong>
		<a href="/" class="btn btn-dark rounded-circle text-light float-end">C</a>
	</h3>
</div>
</div>
</div>
<Vodoo/>