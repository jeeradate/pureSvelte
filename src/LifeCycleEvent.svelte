<script>
    import { onMount, onDestroy, beforeUpdate, afterUpdate } from "svelte";
    let numbers = [];
    let unorderListElement;
    let scrollOn = true;
    let intervalId;
    let bLabel = 'Stop';

    function toggle(){
        if(scrollOn){
            scrollOn = false;
            pushInterval();
            bLabel = 'Run';
        }
        else{
            createInterval();
            bLabel = 'Stop';
        }
    
    }
    function createInterval() {
        intervalId = setInterval(() => {
            numbers = [...numbers, numbers.length + 1];
        }, 1000);
        scrollOn = true;
    }
    function pushInterval() {
        clearInterval(intervalId);
        scrollOn = false;
    }
    onMount(createInterval);
    onDestroy(() => {
        pushInterval();
        console.log("on Destroy");
    });
    beforeUpdate(() => { 
        console.log('before update');
      


    });
    afterUpdate(() => {
        console.log("after Update");
        unorderListElement.scrollTo(0, unorderListElement.scrollHeight);
    });
</script>

<ul bind:this={unorderListElement}>
    {#each numbers as number}
        <li>{number}</li>
    {/each}
</ul>


<button on:click={toggle}>{bLabel}</button><br><br>

<a href="https://github.com/jeeradate/pureSvelte">Source Code Link</a>




<style>
    ul {
        max-height: 150px;
        border: solid black 1px;
        overflow: scroll;
    }
</style>
