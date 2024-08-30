<script>
	import Team from "./Team.svelte";

	let redScore = 5;
	let blueScore = 5;

	let redTeam = "Red";
	let blueTeam = "Blue";
	$: redWon = blueScore === 0;
	$: blueWon = redScore === 0;
	$: gameOver = redWon || blueWon;
	function resetGame() {
		redScore = 5;
		blueScore = 5;
	}
</script>

<h1>MTG Counter App</h1>
<Team team={redTeam} bind:score={redScore} bind:gameOver />
<Team team={blueTeam} bind:score={blueScore} bind:gameOver />

{#if gameOver == true}
	<button on:click={resetGame}>New Game</button>
{:else}
	<button on:click={resetGame}>Reset Game</button>
{/if}

{#if gameOver}
	<h1>The Win Team is {redWon ? redTeam : blueTeam}</h1>
{/if}
<br />
