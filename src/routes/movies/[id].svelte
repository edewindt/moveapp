<script context="module">
	export async function load({ fetch, params }) {
		console.log(params);
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=f36f161798eb48977866fa82bbccb71b&language=en-US`
		);
		const movdet = await res.json();
		console.log(movdet);
		if (res.ok) {
			return {
				props: { movdet }
			};
		}
	}
</script>

<script>
	export let movdet;
	console.log(movdet);
</script>

<div class="mov-det">
	<div class="img-cont">
		<img src={'https://image.tmdb.org/t/p/original' + movdet.backdrop_path} alt={movdet.title} />
	</div>
	<div class="txt-cont">
		<span class="title">
			<h1>{movdet.title}</h1>
		</span>
		<div class="toptxt">
			<p class="overview">{movdet.overview}</p>
		</div>
		<p><span class="bold">Release Date :</span> {movdet.release_date}</p>
		<p><span class="bold">Rating: </span>{movdet.vote_average}</p>
		<p><span class="bold">Length: </span>{movdet.runtime} mins</p>
	</div>
</div>

<style>
	.title {
		margin-bottom: 1rem;
	}
	.toptxt {
		margin-bottom: 1rem;
	}
	.mov-det {
		display: grid;
		grid-template-columns: repeat(3fr);
		justify-content: center;
		background-color: black;
		color: aliceblue;
		padding-bottom: 5%;
	}
	.txt-cont {
		width: 60vw;
		display: flex;
		flex-direction: column;
		font-size: 1.25rem;
		flex-basis: 1;
	}
	img {
		width: 60vw;
		border-radius: 2rem;
	}
	.img-cont {
		margin-bottom: 2rem;
	}
	.bold {
		font-weight: 900;
	}
</style>
