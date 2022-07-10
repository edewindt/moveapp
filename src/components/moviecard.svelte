<script>
	export let movie;
</script>

<a href={'/movies/' + movie.id}>
	<div class="mov-card">
		<img src={'https://image.tmdb.org/t/p/w300' + movie.poster_path} alt="" />
		<div class="descript">
			<h2>{movie.title}</h2>
			<p>Released on <span class="bold">{movie.release_date}</span></p>
		</div>
	</div>
</a>

<style>
	.bold {
		font-weight: 1000;
	}
	img {
		width: 100%;
		object-fit: cover;
		border-radius: 1rem;
		margin-bottom: 1rem;
	}
	.mov-card {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		padding: 1rem;
		background-color: rgba(240, 248, 255, 0);
		transition: 0.5s ease;
		color: black;
	}
	.mov-card:hover {
		background-color: rgb(42, 42, 42);
		color: aliceblue;
		border-radius: 1rem;
	}
	a {
		text-decoration: none;
	}
	@media only screen and (min-width: 1370px) {
		.mov-card:hover {
			transform: scale(1.25);
		}
	}
</style>
