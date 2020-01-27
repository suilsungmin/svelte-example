<script>
	export let name;
	import Nested from './Nested.svelte';

	let numList = []
	let handleClick = () => {
		numList = [
			...numList,
			numList.length + 1
		]
	}
	$: sum = () => {
		let a = 0
		numList.forEach( v => {
			a += v
		})
		return a
	}
</script>

<main>
	<button on:click = {handleClick}>{sum()}</button>
	<Nested answer = {sum()}></Nested>
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