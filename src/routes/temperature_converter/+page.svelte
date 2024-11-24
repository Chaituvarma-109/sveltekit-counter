<script>
    let c = $state(0);
    let f = $state(32);
    let bieq = '<=>'

    function c2f(val) {
        c = val;
        f = (32+(9/5)*c).toFixed(2)
    }

    function f2c(val) {
        f = val;
        c = ((5 / 9) * (f - 32)).toFixed(2);
    }

</script>

<br>

<input type="number" bind:value={c} oninput="{(e) => c2f(e.target.value)}"/>°C {bieq}
<input type="number" bind:value={f} oninput="{(e) => f2c(e.target.value)}"/>°F
