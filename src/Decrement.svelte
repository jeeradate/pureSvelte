<script>
    import {count} from './stores/stores';
    function decrement(){
        count.update((n) => n -1);
    }
</script>
<button on:click={decrement} style="background-color: yellow;">-</button>