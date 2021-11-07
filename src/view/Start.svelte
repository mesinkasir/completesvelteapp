<script>
	import { fade } from 'svelte/transition';
	import { Link } from "svelte-routing";
    import Navbar from "../widget/Nav.svelte";
    import Vodoo from "../widget/fd.svelte";
</script>
<Navbar/>
<div class="container" transition:fade style="opacity:0.8;">
<div class="row p-3">
<div class="col-12 col-md-6 p-3 p-md-5">
<h1 style="color:#f9cb9c;"><strong>Welcome to family !!</strong></h1>
<p class="lead">This is an example project develope using svelte, download now and learn svelte<br/><small>Special thanks to svelte, host by cloudflare repo on github , support by hockeycomp - axcora and developer creativebydre</small></p>
<p>And if you need to develope modern website and application or all in one modern website + android application you can call us.<br/>Whatsapp : +6285646104747 <br/>Email : axcora@gmail.com</p>
<a href="https://www.hockeycomputindo.com/2021/11/all-in-one-web-app-svelte-free-download.html" class="border border-secondary p-1 text-dark" style="text-decoration: none;">Documentation →</a>
</div>
<div class="col-12 col-md-6 p-1">
<div class="row" style="background-color:#f9cb9c;">
<Link to="/pos" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-pc-display-horizontal" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M1.5 0A1.5 1.5 0 0 0 0 1.5v7A1.5 1.5 0 0 0 1.5 10H6v1H1a1 1 0 0 0-1 1v3a1 1 0 0 0 1 1h14a1 1 0 0 0 1-1v-3a1 1 0 0 0-1-1h-5v-1h4.5A1.5 1.5 0 0 0 16 8.5v-7A1.5 1.5 0 0 0 14.5 0h-13Zm0 1a.5.5 0 0 0-.5.5v7a.5.5 0 0 0 .5.5h13a.5.5 0 0 0 .5-.5v-7a.5.5 0 0 0-.5-.5h-13ZM12 12.5a.5.5 0 1 1 1 0 .5.5 0 0 1-1 0Zm2 0a.5.5 0 1 1 1 0 .5.5 0 0 1-1 0ZM1.5 12a.5.5 0 0 0 0 1h5a.5.5 0 0 0 0-1h-5ZM1 14.25a.25.25 0 0 1 .25-.25h5.5a.25.25 0 1 1 0 .5h-5.5a.25.25 0 0 1-.25-.25Z"/>
</svg>
<br/>
Point Of Sale
</Link>
<Link to="/stock" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-box-seam" viewBox="0 0 16 16">
  <path d="M8.186 1.113a.5.5 0 0 0-.372 0L1.846 3.5l2.404.961L10.404 2l-2.218-.887zm3.564 1.426L5.596 5 8 5.961 14.154 3.5l-2.404-.961zm3.25 1.7-6.5 2.6v7.922l6.5-2.6V4.24zM7.5 14.762V6.838L1 4.239v7.923l6.5 2.6zM7.443.184a1.5 1.5 0 0 1 1.114 0l7.129 2.852A.5.5 0 0 1 16 3.5v8.662a1 1 0 0 1-.629.928l-7.185 2.874a.5.5 0 0 1-.372 0L.63 13.09a1 1 0 0 1-.63-.928V3.5a.5.5 0 0 1 .314-.464L7.443.184z"/>
</svg> 
<br/>
Inventori
</Link>
<Link to="/template" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-images" viewBox="0 0 16 16">
  <path d="M4.502 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z"/>
  <path d="M14.002 13a2 2 0 0 1-2 2h-10a2 2 0 0 1-2-2V5A2 2 0 0 1 2 3a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2v8a2 2 0 0 1-1.998 2zM14 2H4a1 1 0 0 0-1 1h9.002a2 2 0 0 1 2 2v7A1 1 0 0 0 15 11V3a1 1 0 0 0-1-1zM2.002 4a1 1 0 0 0-1 1v8l2.646-2.354a.5.5 0 0 1 .63-.062l2.66 1.773 3.71-3.71a.5.5 0 0 1 .577-.094l1.777 1.947V5a1 1 0 0 0-1-1h-10z"/>
</svg>
<br/>
Web Themes
</Link>
<Link to="/agenda" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-easel2" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M8 0a.5.5 0 0 1 .447.276L8.81 1h4.69A1.5 1.5 0 0 1 15 2.5V11h.5a.5.5 0 0 1 0 1h-2.86l.845 3.379a.5.5 0 0 1-.97.242L12.11 14H3.89l-.405 1.621a.5.5 0 0 1-.97-.242L3.36 12H.5a.5.5 0 0 1 0-1H1V2.5A1.5 1.5 0 0 1 2.5 1h4.691l.362-.724A.5.5 0 0 1 8 0ZM2 11h12V2.5a.5.5 0 0 0-.5-.5h-11a.5.5 0 0 0-.5.5V11Zm9.61 1H4.39l-.25 1h7.72l-.25-1Z"/>
</svg>
<br/>
Agenda
</Link>
<Link to="/" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-headset" viewBox="0 0 16 16">
  <path d="M8 1a5 5 0 0 0-5 5v1h1a1 1 0 0 1 1 1v3a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6a6 6 0 1 1 12 0v6a2.5 2.5 0 0 1-2.5 2.5H9.366a1 1 0 0 1-.866.5h-1a1 1 0 1 1 0-2h1a1 1 0 0 1 .866.5H11.5A1.5 1.5 0 0 0 13 12h-1a1 1 0 0 1-1-1V8a1 1 0 0 1 1-1h1V6a5 5 0 0 0-5-5z"/>
</svg>
<br/>
Chat
</Link>
<a href="https://github.com/mesinkasir/completesvelteapp.git" class="btn btn-outline-dark col-6 col-md-4 p-3">
<svg xmlns="http://www.w3.org/2000/svg" width="126" height="126" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
</svg>
<br/>
Github
</a>
</div>
</div>
</div>
</div>
<Vodoo/>