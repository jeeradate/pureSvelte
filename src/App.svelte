<script>
	import Team from "./Team.svelte";
	let helpon = false;
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
	function Help(){
		helpon = !helpon;
		
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
<button on:click={Help}>Help</button>
{#if helpon}
	<div> 
		<h2>Help</h2>
		<p>โปรแกรมนี้เป็นโปรแกรมช่วยนับแต้มการแข่งขันของทีม Red และทีม Blue</p>
		<br>
		<p>กดเพิ่มและลดคะแนนในแต่ละทีมได้ หากทีมไหนได้คะแนเป็น ศูนย์ 0 ก่อน อีกทีม จะชนะ </p><br>
		<p>กด Reset Game เพื่อตั้งต้นใหม่ </p> <br>
		<p>หรือกด New Game เพื่อเล่นอีกเกมส์</p>
	</div>
{/if}
