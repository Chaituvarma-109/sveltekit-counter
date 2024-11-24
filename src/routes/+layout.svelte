<script>
    let {children} = $props();
</script>


<nav>
    <a href="/">Home</a>
    <a href="/counter">counter</a>
    <a href="/blog">blog</a>
    <a href="/temperature_converter">Temperature Converter</a>
    <a href="/flightbooking">Flight Booking</a>
    <a href="/timer">Timer</a>
    <a href="/tasks">tasks</a>
</nav>

{@render children()}
