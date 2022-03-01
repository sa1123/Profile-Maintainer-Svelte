<script>
	import Modal from './Modal.svelte';

	let showModal = false;

	const toggleModal = () => {
		showModal = !showModal;
	}

	let people = [
		{ name: 'Yoshi', beltColor: 'green', age: 25, id: 1},
		{ name: 'Mario', beltColor: 'red', age: 30, id: 2},
		{ name: 'Mr. Game&Watch', beltColor: 'black', age: 35, id: 3}
	];

	const handleClick = (id) => {
		people = people.filter((person) => person.id != id);
	}

</script>

<Modal message="Hey there again" {showModal} on:click={toggleModal}/>
<main>
	<button on:click={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
		<div>
			<h3>{person.name}</h3>
			{#if person.beltColor === 'black'}
				<p><strong>Master Ninja</strong></p>
			{/if}
			<p>{person.age} years old, {person.beltColor} belt</p>
			<button on:click={() => handleClick(person.id)}>Delete</button>
		</div>
	{:else}
		<p>There are no people</p>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>