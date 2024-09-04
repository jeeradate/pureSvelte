<script>
    import { count } from "./stores/stores";
    import Increment from "./Increment.svelte";
    import Decrement from "./Decrement.svelte";
    import Reset from "./Reset.svelte";
    let countValue;
    count.subscribe((value) => (countValue = value));
</script>

<h1>The count is {countValue} ok</h1>
<Increment />
<Decrement />
<Reset />
<br>
<br>
<p>This is for learning Svelte</p>
<a href="https://github.com/jeeradate/pureSvelte">Source code Link</a>
