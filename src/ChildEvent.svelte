<script>
    import {createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();
    function handleClick(){
        dispatch('custom_event',{
           message: Math.random()
    });
    }
</script>

<div on:click={handleClick}></div>

<style>
    div {
        width: 90%;
        height: 300px;
        margin-top: 30px;
        background-color: aquamarine;
    }
</style>
