<script>
    import { fade, fly } from 'svelte/transition';
    import Navbar from "../widget/Nav.svelte";
    import Vodoo from "../widget/fd.svelte";
	let webs = [
		{ img: 'https://camo.githubusercontent.com/373d5753891827fa96a2e647b5fbe1b97f2c10f29b5772ecc7198e988e3b8fac/68747470733a2f2f312e62702e626c6f6773706f742e636f6d2f2d6152674a7070364e674b632f59585a736c51655f776d492f41414141414141415266672f617345476d614348736e3875325647432d476339744275656d72546c7034573067434c63424741735948512f73313032342f66726565253242736f75726365253242636f64652532427765627369746525324274656d706c6174652532427468656d65732532427361707065722532427376656c746525324267726174697325324225323532383125323532392e6a7067',
		name: 'Sapper Svelte Black White',
		description: 'Using Tailwind feat Bootstrap Sapper Svelte Black White website template themes',
		url: 'https://github.com/mesinkasir/sapper-blackwhite',
		},
		{ img: 'https://camo.githubusercontent.com/120eaa2aca8dfd70ca050a20e44213dbbe7355d54f4a0fcd4e2da1dda45b0b29/68747470733a2f2f312e62702e626c6f6773706f742e636f6d2f2d4557524b527832694e43732f5958514672733230724c492f41414141414141415264342f7838474e334530764f486b2d4763454d374142646c75707947676c30796b663867434c63424741735948512f73313336362f7376656c7465253242736f75726365253242636f646525324277656225324261707025324225323532383925323532392e706e67',
		name: 'Svelte Native MDL',
		description: 'A template develope using MDL with mobile version display',
		url: 'https://github.com/mesinkasir/sveltemdl',
		},
		
		{ img: 'https://camo.githubusercontent.com/79ed08bcb574743f63e1ae09150478eaa2ce23b3fc7e3009857ff88e368994e7/68747470733a2f2f312e62702e626c6f6773706f742e636f6d2f2d43443674492d39527144452f595844553731616e7957492f414141414141414152614d2f7070476e745f4f623074636533675233494e703656564c655f51395547475f6577434c63424741735948512f73323034382f7376656c746525324262756d6125324274656d706c61746525324225323532383125323532392e706e67',
		name: 'Svelte Bulma',
		description: 'A template develope using Bulma with 3D Animation display',
		url: 'https://github.com/mesinkasir/svelte-bulma',
		},
		
		{ img: 'https://github.com/mesinkasir/bootstrapsvelte/raw/main/home.png',
		name: 'Svelte Bootstrap',
		description: 'Develope using Bootstrap framework with Landing Page display',
		url: 'https://github.com/mesinkasir/bootstrapsvelte',
		}
	];
</script>
<Navbar/>
<div class="container"  style="opacity:0.8;" transition:fly="{{ y: 800, duration: 2000 }}">
<div class="row">
<div class="col-12 p-3 p-md-5">
<h1 style="color:#f9cb9c;"><strong>Our Project Website Template</strong></h1>
<p class="lead">Open source code and free download svelte website template themes.</p>
<div class="row">
	{#each webs as { img, name ,url , description}, i}
		<div class="col-6 p-3 p-md-5"><a target="_blank" class="text-secondary" style="text-decoration: none;" href="{url}">
		<img class="img-fluid" alt="web templates" src="{img}"/>
			{i + 1}. {name}<br/>{description}
		</a>
		</div>
	{/each}
</div>
</div>
</div>
</div>
<Vodoo/>