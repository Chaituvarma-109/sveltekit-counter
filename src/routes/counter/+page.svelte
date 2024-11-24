<script>
    let count = $state(0);
</script>

<h1>This is counter app</h1>

<input type="number" bind:value={count} disabled/>

<button onclick="{() => count++}">+</button>
