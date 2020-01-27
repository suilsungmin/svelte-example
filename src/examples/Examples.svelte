<script>
	import Nested from './Nested.svelte';
	import PromiseTest from './PromiseTest.svelte';
	import DomEvents from './DomEvents.svelte';
	import DispatcherTest from './DispatcherTest.svelte';
	import BindTest from './BindTest.svelte';
	export let name;
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
	const onMessage = (e) => {
		alert(e.detail.text)
	}
</script>

<div id="examples">
	<button on:click = {handleClick}>{sum()}</button>
	<Nested answer = {sum()}></Nested>
	<PromiseTest />
	<DomEvents />
	<DispatcherTest on:message={onMessage}/>
	<BindTest/>
</div>

<style>

	#examples {
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
		#examples {
			max-width: none;
		}
	}
</style>