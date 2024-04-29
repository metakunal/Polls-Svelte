<script>
let name;
let beltColour;
let age;

const handleSubmit=()=>{
    console.log(name,beltColour,age)
}
</script>

<form on:submit|preventDefault={handleSubmit}>
	<input type="text" placeholder="Add Name" bind:value={name}>
	<input type="text" placeholder="Add Belt Color" bind:value={beltColour}>
    <input type="number" placeholder="Add Age" bind:value={age}>
	<button>Add Ninja</button>
</form>

<style>

</style>