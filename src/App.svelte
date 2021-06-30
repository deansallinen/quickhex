<script>
	const genID = () => `0x${Math.floor(Math.random() * 256**3).toString(16).padStart(6, '0')}`
</script>

<main>
	<h1>{genID()}</h1>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
