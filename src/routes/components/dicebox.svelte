<script lang="ts">
	import D1 from '../res/dice/1.webp';
	import D2 from '../res/dice/2.webp';
	import D3 from '../res/dice/3.webp';
	import D4 from '../res/dice/4.webp';
	import D5 from '../res/dice/5.webp';
	import D6 from '../res/dice/6.webp';
	import D0 from '../res/dice/diceanim.gif';

	let diceface = D0;
	let dicecount = 0;

	export let year = 0;
	const maxYear = 60;

	function restartGame() {
		diceface = D0;
		dicecount = 0;
		year = 0;
	}

	function rollDice() {
		diceface = D0;

		if (year >= maxYear) {
			alert('You’ve reached the end of your journey!');
			return;
		}

		setTimeout(() => {
			dicecount = Math.floor(Math.random() * 6) + 1;
			diceface = [D1, D2, D3, D4, D5, D6][dicecount - 1];
			year = Math.min(year + dicecount, maxYear);
		}, 1000);
	}
</script>

<div id="game-container">
	<div id="status-bar">
		<h2>Year of Life: {year}</h2>
		<div id="progress-bar">
			<div id="progress" style="width: {(year / maxYear) * 100}%"></div>
		</div>
	</div>

	<div id="dice-container">
		<img class="dice-img" src={diceface} alt="dice" />
	</div>

	<div id="controls">
		<button class="control-button" on:click={rollDice}>Roll the Dice</button>
		<button class="control-button" on:click={restartGame}>Restart Journey</button>
	</div>
</div>

<style>
	/* Container for the entire game interface */
	#game-container {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 80vh;
		background-color: #222;
		color: #fff;
		border-radius: 15px;
		padding: 20px;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
	}

	/* Status bar to display current year and progress */
	#status-bar {
		width: 100%;
		text-align: center;
	}

	#status-bar h2 {
		font-size: 2rem;
		margin-bottom: 10px;
		color: #f2f2f2;
	}

	#progress-bar {
		width: 80%;
		height: 15px;
		background-color: #444;
		border-radius: 10px;
		overflow: hidden;
		margin: 10px auto;
	}

	#progress {
		height: 100%;
		background-color: #28a745;
		border-radius: 10px;
		transition: width 0.4s ease;
	}

	/* Dice image styling */
	#dice-container {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 150px;
		height: 150px;
	}

	.dice-img {
		width: 100%;
		height: auto;
		transition: transform 0.5s ease;
	}

	/* Styling for control buttons */
	#controls {
		width: 100%;
		display: flex;
		justify-content: space-evenly;
		margin-top: 20px;
	}

	.control-button {
		padding: 15px 25px;
		font-size: 1.25rem;
		background-color: #28a745;
		color: #fff;
		border: none;
		border-radius: 8px;
		cursor: pointer;
		transition: background-color 0.3s ease, transform 0.3s ease;
	}

	.control-button:hover {
		background-color: #218838;
		transform: scale(1.05);
	}

	.control-button:active {
		transform: scale(0.95);
	}

	@media (max-width: 768px) {
		#game-container {
			height: 40vh;
			padding: 10px;
			margin: 10px auto;
		}

		#status-bar h2 {
			font-size: 1.5rem;
		}

		.dice-img {
			width: 80px;
		}
		#dice-container{
			width: 100px;
			height: 100px;
		}

		.control-button {
			font-size: 0.9rem;
			padding: 5px 10px;
		}
	}
</style>
