<script>
    import { createEventDispatcher } from 'svelte';
  
    let count = 0;
    const dispatch = createEventDispatcher();
  
    function handleClick() {
      count += 1;
      dispatch('counter-clicked', {
        clicks: 1
      });
    }
  </script>
  
  <button on:click={handleClick}>
    Clicked {count} {count == 1 ? 'time' : 'times'}
  </button>