<script>
import Coolapp from "./Coolapp.svelte";

</script>

<main>
	<h1>Cool App!</h1>
	<Coolapp />
</main>

<style>
	main {
		
		text-align: center;
		padding: 1em;
		max-width: 100vw;
		max-height: 100;
		margin: 0 auto;
		
	}
	
	h1 {
		color: #f08080;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 500;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
