<script>
    import {count} from './stores/stores';
    function reset(){
        count.set(0);
    }
</script>
<button on:click={reset} style="background-color: goldenrod;">reset</button>