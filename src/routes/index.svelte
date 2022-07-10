<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=f36f161798eb48977866fa82bbccb71b&language=en-US`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import Popmov from '../components/popmov.svelte';
	export let popular;
	console.log(popular);
	import Searchmov from '../components/searchmov.svelte';
</script>

<section>
	<Popmov {popular} />
</section>

<style>
	section {
		background-color: aliceblue;
		border-radius: 1rem;
	}
	@media only screen and (min-width: 1370px) {
		* {
			margin: 0px 300px;
		}
	}
	* {
		margin-bottom: 3rem;
	}
</style>
