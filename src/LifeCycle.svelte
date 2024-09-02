<script>
    import {onMount} from 'svelte';
    let quote = '';
    let author = '';
    let error = false;
    let loading = true;
    onMount(async () => {
        try {
            const url = 'https://zenquotes.io/api/random/';
            const response = await fetch(url);
            const [quoteMessage] = await response.json();
            quote = quoteMessage.q;
            author = quoteMessage.a;

            loading = false;
        } catch (e){
            error = true;
        }
        loading = false;
      
        
    });
    import {onDestroy} from 'svelte';
    onDestroy(() => {
        console.log('on destroy');
    })

</script>

{#if loading}
<h2>Loading...</h2>

{:else if error}
<h2>Loading Error </h2>

{:else}
    <h2>{quote}</h2>
    <h3>{author}</h3>

{/if}
<p>This component need to run in Chrome with CORS extension enable</p>
<p>Refresh this page to show different quote</p>
<p><a href="https://github.com/jeeradate/pureSvelte">Source code</a></p>