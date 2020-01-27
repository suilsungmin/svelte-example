<script>
	import Examples from './examples/Examples.svelte';
	import Todo from './todo/Todo.svelte';
	let menus = [ 'Examples', 'Todo']
	let selectedMenu = "Examples"
	const onClickMenu = (e) => {
		console.log(e.target.value)
		selectedMenu = e.target.value
	}
</script>

<main>
	<div id ='top-menu'>
		{#each menus as menu}
			<button on:click={onClickMenu} value ={menu}>
				{menu}
			</button>
		{/each}
	</div>
	{#if selectedMenu == "Examples"}
		<Examples />
	{:else}
		<Todo />
	
	{/if}
</main>

<style>
	#top-menu{
		width : 100%;
		
		display: flex;
		flex : .2;
	}
	button  {
		flex : 1;
	}
</style>