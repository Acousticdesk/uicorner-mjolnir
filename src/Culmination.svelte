<script>
    export let name
    export let authorize
</script>

<p>Hi, {name}! So you think you deserve to hold Mjolnir! Hahahaa!</p>

<button
    type="button"
    on:click={authorize}
>
    Test me!
</button>
