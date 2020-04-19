<script>
import ContactCard from './ContactCard.svelte';

	let name = 'Aviral';
	let age = 25;
	let title="";
	let description = "";
	let image="";

	function increaseAge() {
		age += 1;
	}
	function inputChange(event) {
		name = event.target.value
	}
	function changeName() {
		name = 'Yadav ji'
	}
	// let uppercaseName;
	$: uppercaseName = name.toUpperCase();  ///// for reactivity,dynamic changes " $: expression "
	$: console.log('excuted', uppercaseName);
	$: if(name === 'Aviral') {
		age = 40
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Name {uppercaseName}!</h1>
<h1>Age {age}!</h1>
<button on:click="{increaseAge}">Increase Age</button>
<button on:click="{changeName}">Change Name</button>
<!-- <input type="text" value="{name}" on:input="{inputChange}"> -->
<input type="text" bind:value="{name}" >
<input type="text" bind:value="{title}" >
<input type="text" bind:value="{description}" >
<input type="text" bind:value="{image}" >

<ContactCard userName="{name}" jobTitle={title} {description} imageUrl={image} />
