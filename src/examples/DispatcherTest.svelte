<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	function sayHello() {
		dispatch('message', {
			text: 'Hello!'
		});
	}
</script>


<div>
    <button on:click={sayHello}>sayHello dispatcher</button>
</div>