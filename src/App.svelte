<script>
  import { handle_promise } from "svelte/internal";

	let firstName="Kunal";
	let lastName="Yadav"
	let beltColour="black"

	//Reactive Values
	$: fullName=`${firstName} ${lastName}`
	//Reactive Statements
	$: {
		console.log(firstName);
		console.log(beltColour)
	}
	// let setColour=()=>{
	// 	beltColour="Orange";
	// }
	// let handleInput=(e)=>{
	// 	beltColour=e.target.value;
	// }
</script>

<main>
	<h1>{fullName} {beltColour} belt</h1>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
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