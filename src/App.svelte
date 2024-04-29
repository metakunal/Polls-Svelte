<script>
import Modal from "./Modal.svelte"
import AddPersonForm from './AddPersonForm.svelte'
let people = [
    { name: 'yoshi', beltColour: 'black', age: 25, id: 1 },
    { name: 'mario', beltColour: 'orange', age: 45, id: 2 },
    { name: 'luigi', beltColour: 'brown', age: 35, id: 3 }
  ];
  let handleDelete=(id)=>{
	people=people.filter((person)=>id!=person.id)
  }

  
  let showModal = false;

  let toggleModal = () => {
    showModal = !showModal;
  };
</script>

<Modal message="Hey, I am a Model" {showModal} on:click={toggleModal}>
<AddPersonForm/>
</Modal>
<main>
	<button on:click|once={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
	<div>
		{#if person.beltColour==="black"}
		<b>MASTER NINJA</b>
		{/if}
		<h4>{person.name}</h4>
		<p>{person.age} years old, {person.beltColour} belt</p>
	</div>
	<button on:click={()=>handleDelete(person.id)}>Delete</button>
	{:else}
		<p>There are no people to show</p>
	{/each}
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