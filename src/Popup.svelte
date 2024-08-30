<script>
    import {createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();


</script>

<h1>Popup window</h1>
<button on:click={() => dispatch('close','Messg')}>Close Popup</button>