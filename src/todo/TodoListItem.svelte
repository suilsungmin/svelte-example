<script>
    export let done;
    export let todo;
    export let handleItemClick; 
    export let handleItemChange;
</script>


<div>
    <input type=checkbox checked={done} on:change={handleItemClick}>
    <input type=text value={todo} on:change={handleItemChange}>
</div>