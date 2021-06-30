<script>
	export let len = 6;
	let randHex = function(len) {
  		let maxlen = 8
      		let min = Math.pow(16,Math.min(len,maxlen)-1) 
      		let max = Math.pow(16,Math.min(len,maxlen)) - 1
      		let n = Math.floor( Math.random() * (max-min+1) ) + min
      		let r = n.toString(16);
  		while ( r.length < len ) {
     			r = r + randHex( len - maxlen );
  		}
  		return r;
	};
</script>

<main>
	<h1>Hello {randHex()}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
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
