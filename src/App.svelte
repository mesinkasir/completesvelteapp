<script>
	import { Router, Route } from "svelte-routing";
	import Index from "./view/Index.svelte";
	import Start from "./view/Start.svelte";
	import Pos from "./view/Pos.svelte";
	import Stock from "./view/Stock.svelte";
	import Agenda from "./view/Agenda.svelte";
	import Chat from "./view/Chat.svelte";
	import Tema from "./view/Themes.svelte";
  
	export let url = "";
  </script>
    <Router url="{url}">
	<Route path="/" component="{Index}" />
	<Route path="/pos" component="{Pos}" />
	<Route path="/stock" component="{Stock}" />
	<Route path="/start" component="{Start}" />
	<Route path="/agenda" component="{Agenda}" />
	<Route path="/chat" component="{Chat}" />
	<Route path="/template" component="{Tema}" />
  </Router>
