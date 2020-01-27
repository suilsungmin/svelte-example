<script>
    const promise = () => {
        return new Promise((resolve) => {
            setTimeout( () => {
                resolve( 3)
            }, 1000)
        })
    }
    const promise2 = () => {
        return new Promise((resolve) => {
        setTimeout( () => {
            resolve( 5)
        }, 2000)
    })
    }
    const getRandomNumber = async() => {
        const values = await Promise.all( [promise(), promise2()])
        return values[0] + values[1]
    };
    let a = getRandomNumber()
    const handleClick = () => {
        a = getRandomNumber()
    }
</script>

<div>
    Async promise TEST
</div>
<button on:click={handleClick}>Promise call</button>
{#await a then value}
	<p>the value is {value}</p>
{/await}