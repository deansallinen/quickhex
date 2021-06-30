<script>
	import { onMount } from "svelte";
	import confetti from "canvas-confetti";
	import { fade } from "svelte/transition";
	const genHex = () => `0x${Math.floor(Math.random() * 256**3).toString(16).padStart(6, '0')}`
	let hex;
	onMount(() => {
    		confetti.create(document.getElementById("canvas"), {
      			resize: true,
      			useWorker: true
    		})({ particleCount: 200, spread: 200, origin: { y: 0.45 } });
    		hex = genHex();
  	});
</script>

<svelte:head>
  <title>QuickHex</title>
</svelte:head>

<main>
{#if hex}
    <h1 transition:fade={{ duration: 200 }}>{hex}</h1>
  {/if}
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
