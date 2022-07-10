<script>
	let searchval = '';
	import { goto } from '$app/navigation';
	function sub() {
		goto('/search/' + searchval);
	}
</script>

<div class="nother">
	<div class="all">
		<form on:submit|preventDefault={sub} class="search">
			<label for="search">Search</label>
			<input bind:value={searchval} name="search" type="text" placeholder="Search Movie" />
			<button>Search</button>
		</form>
	</div>
</div>

<style>
	button {
		background-color: black;
		color: whitesmoke;
		border: none;
		padding: 0.5rem;
		border-radius: 0.5rem;
		font-size: 1.25rem;
		font-weight: 600;
		transition: 0.5s;
	}
	input {
		height: 1.6rem;
		border-radius: 0.5rem;
	}
	button:hover {
		background-color: rgb(255, 175, 252);
		color: black;
	}

	form input {
		height: 2rem;
	}
	form label {
		font-size: 1.5rem;
	}
	input::placeholder {
		text-align: center;
		font-size: 1.25rem;
	}
	.all {
		display: flex;
		justify-content: center;
		margin: 1rem 0;
	}
</style>
