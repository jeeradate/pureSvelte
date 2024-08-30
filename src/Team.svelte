<script>


export let team ;
export let score;
export let gameOver;
function increase(){
    score += 1;
}
function decrease(){
    score -= 1;
}
</script>
<br>
<div >
	<h2>{team} Team score = {score}</h2>
		<button disabled={gameOver} on:click={increase}>{team} increase</button>
		<button disabled={gameOver} on:click={decrease}>{team} decrease</button>
</div>

<style>
    div {
        border-style: dashed;
     }
</style>