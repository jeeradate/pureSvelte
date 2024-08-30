<script>
   import {createEventDispatcher} from 'svelte';
   const disp = createEventDispatcher();

   
   let name = 'blue';
    let age = 33;
    function submitHandle(e){
         
         disp('form_submit',{
            name,
            age,
         });
    }
</script>

<h2>Form</h2>
<form on:submit|preventDefault={submitHandle}>
<label for="name">Enter Name:</label>
<input type="text" bind:value={name} id="name" autocomplete="name"/>
<label for="age">Enter age:</label>
<input type="number" bind:value={age} id="age" />
<button type="submit">Submit</button>
</form>
<button on:click={()=> alert("Hello form")}>Click me </button>
{name}
{age}

