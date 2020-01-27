<script>
    let a = "";
    let checked = false;
</script>
<p>Bind Value TEST input val : {a}</p>
<input type=range bind:value={a} />
<p>bind Checkbox val : {checked} </p>
<input type=checkbox bind:checked={checked} />