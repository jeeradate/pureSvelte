<script>
    import { createEventDispatcher } from 'svelte';
    
    export let id;
    export let text;
    export let completed = false;
    
    const dispatch = createEventDispatcher();
  
    function toggleComplete() {
      dispatch('toggle', {
        id: id,
        completed: !completed
      });
    }
  </script>
  
  <li>
    <input type="checkbox" checked={completed} on:change={toggleComplete}>
    <span class:completed>{text}</span>
  </li>
  
  <style>
    .completed {
      text-decoration: line-through;
    }
  </style>