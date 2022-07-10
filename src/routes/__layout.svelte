<script>
	import global from '../global.css';
	import Searchmov from '../components/searchmov.svelte';
	import Nav from '../components/nav.svelte';
	import Footer from '../components/footer.svelte';
</script>

<svelte:head>
	<title>Unflix</title>
</svelte:head>
<Nav />
<Searchmov />

<slot />
<Footer />
