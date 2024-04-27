<script>
  import { handle_promise } from "svelte/internal";

	let name="World";
	let beltColour="black"
	let setColour=()=>{
		beltColour="Orange";
	}
	let handleInput=(e)=>{
		beltColour=e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {beltColour};">You are {beltColour} belt</p>
	<button on:click={setColour}>Set Colour</button>
	<!-- <input type="text" on:input={handleInput} value={beltColour}> -->
	<!-- One Way data binding -->
	<input type="text" bind:value={beltColour}>
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