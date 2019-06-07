<script>
    export let value = ''
    export let disabled
</script>

<input disabled={disabled} type="text" bind:value={value}>