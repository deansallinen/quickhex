<script>
	import { onMount } from "svelte";
	import confetti from "canvas-confetti";
	import { fade } from "svelte/transition";
	const genHex = () => `#${Math.floor(Math.random() * 256**3).toString(16).padStart(6, '0')}`
	let hex;
	let textColor;
	function getContrastYIQ(hexcolor){
		hexcolor = hexcolor.replace("#", "");
		var r = parseInt(hexcolor.substr(0,2),16);
		var g = parseInt(hexcolor.substr(2,2),16);
		var b = parseInt(hexcolor.substr(4,2),16);
		var yiq = ((r*299)+(g*587)+(b*114))/1000;
		return (yiq >= 128) ? '#333' : '#eee';
	}
onMount(() => {
    		confetti.create(document.getElementById("canvas"), {
      			resize: true,
      			useWorker: true
    		})({ particleCount: 200, spread: 200, origin: { y: 0.45 } });
    		hex = genHex();
		textColor = getContrastYIQ(hex);
  	});
</script>

{#if hex}
<main style="background:{hex}; color:{textColor}">
    <h1 transition:fade={{ duration: 200 }}>{hex}</h1>
</main>
  {/if}

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

