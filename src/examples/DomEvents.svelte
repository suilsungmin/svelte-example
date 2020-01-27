<script>
    let m = {
        x: 0, 
        y: 0
    }
    const handleMouseMove = (e) => {
        m = {
            x : e.clientX,
            y : e.clientY
        }
    }
</script>

<style>
    div {
        width : 100%;
        height : 200px;
        background-color : blueviolet;
        display: flex;
        flex-direction: row;
        align-self: center;
        justify-content: center;
    }
</style>
<p>mousemove.</p>
<div on:mousemove= {handleMouseMove}>
    <p>mouse cursor. X : {m.x} / Y : {m.y}</p>
</div>
<!-- <div on:mousemove= "{e => m = {x : e.clientX, y : e.clientY}}"> // inline handler
    <p>mouse cursor. X : {m.x} / Y : {m.y}</p>
</div> -->