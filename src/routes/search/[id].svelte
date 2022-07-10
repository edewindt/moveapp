<script context="module">
	export async function load({ fetch, params }) {
		console.log(params);
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=f36f161798eb48977866fa82bbccb71b&language=en-US&query=${params.id}&page=1&include_adult=false`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { searched: data.results }
			};
		}
	}
</script>

<script>
	import Moviecard from '../../components/moviecard.svelte';
	export let searched;
</script>

<div class="searched">
	{#each searched as movie}
		<Moviecard {movie} />
	{/each}
</div>

<style>
	.searched {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 0.5rem;
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
