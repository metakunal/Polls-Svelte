<script>

import {createEventDispatcher} from 'svelte';

let dispatch=createEventDispatcher();
let name;
let beltColour;
let age;
let skills=[];

const handleSubmit=()=>{
    const person={
        name,
        beltColour,
        age,
        skills,
        id:Math.random()
    }
    dispatch('addPerson',person)
};

</script>

<form on:submit|preventDefault={handleSubmit}>
	<input type="text" placeholder="Add Name" bind:value={name}>
    <input type="number" placeholder="Add Age" bind:value={age}>
    <label>Skills</label>
    <input type="checkbox" bind:group={skills} value="fighting">Fighting <br>
    <input type="checkbox" bind:group={skills} value="sneaking">Sneaking <br>
    <input type="checkbox" bind:group={skills} value="running">Running <br>
    <label>Belt Colour : </label>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="yellow">yellow</option>
        <option value="brown">brown</option>
    </select>
	<button>Add Ninja</button>
</form>

<style>

</style>