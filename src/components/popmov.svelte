<script>
	import Moviecard from './moviecard.svelte';
	export let popular;
	console.log(popular[0]);
</script>

<h3>Popular Movies</h3>

<div class="pop-mov">
	{#each popular as movie}
		<Moviecard {movie} />
	{/each}
</div>

<style>
	h3 {
		display: flex;
		justify-content: center;
		padding: 1rem;
	}
	.pop-mov {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 0.5rem;
	}
</style>
