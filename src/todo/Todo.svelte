<script>
    import TodoListItem from './TodoListItem.svelte';
    let initListItem = {
        todo : '',
        done : false
    }
    let todoList = []
    const addItem = () => {
        todoList = todoList.concat(initListItem)
        console.log(todoList)
    }
    const handleItemClick = (idx, e) => {
        let a = {
            ...todoList[idx],
            done : e.target.checked
        }
        let todoList = [
            ...todoList.splice(0, idx),
            a,
            ...todoList.splice(idx +1)
        ]
    }
    const handleItemChange = (idx, e) => {
        let a = {
            ...todoList[idx],
            todo : e.target.value
        }
        let todoList = [
            ...todoList.splice(0, idx),
            a,
            ...todoList.splice(idx +1)
        ]
    }
</script>

<div id="todo-list">
    <h2>TodoList</h2>
    <div id="action-button-wrapper">
        <button on:click={addItem}>ADD</button>
        <button>REMOVE</button>
    </div>
    {#each todoList as todo, idx}
        <TodoListItem  {...todo} handleItemChange = {handleItemChange.bind(this, idx)} 
                        handleItemClick = {handleItemClick.bind(this, idx)} />
    {/each}

</div>


<style>
</style>