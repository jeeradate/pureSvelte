<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
  
    function sendMessage() {
      dispatch('age', {
        text: 'Hello from child!',
        id: 1
      });
    }
  </script>
  
  <button on:click={sendMessage}>Send Message</button>