<script>
	const genID = () => `0x${Math.floor(Math.random() * 256**3).toString(16).padStart(6, '0')}`
</script>

<main>
	<h1>{genID()}</h1>
</main>

<style>
  main {
    display: flex;
    height: 100vh;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    max-width: 240px;
    margin: 0 auto;
  }
  h1 {
    font-size: 5vw;
    font-weight: bold;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
