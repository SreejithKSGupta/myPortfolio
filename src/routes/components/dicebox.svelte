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
    
    export let dicestage = 0;

    
    function startagain() {
        diceface = D0;
        dicecount = 0;
        dicestage = 0;
    }

    
	function spindice() {
		diceface = D0;
        if(dicestage > 60){
                dicestage = 60;
                alert("You have reached the end of the Game");
                return;
            }
		setTimeout(() => {
			dicecount = Math.floor(Math.random() * 6) + 1;
			diceface = 0
				? D0
				: dicecount == 1
				? D1
				: dicecount == 2
				? D2
				: dicecount == 3
				? D3
				: dicecount == 4
				? D4
				: dicecount == 5
				? D5
				: D6;
			dicestage = dicecount + dicestage;
         
		}, 1000);
	}
</script>

<div id="dicebox">
	<h3>Roll the dice and see My life..</h3>
	<div id="dice"><img class="diceimg" src={diceface} alt="dice" /></div>
	<div id="controller">
		<button class="diceroller" on:click={startagain}>Start Again</button>
        <button class="diceroller" on:click={spindice}>Roll Dice</button
		><button class="diceroller">Stage : {dicestage}</button>
	</div>
</div>

<style>
    h3{
        font-size: 2rem;
        font-weight: 500;
        text-align: center;
        color: white;
    }
	#dicebox {
		width: 100%;
		height: 60vh;
		border-radius: 10px;
		margin: 5vh auto;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		align-items: center;
	}
    #controller{
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
        align-items: center;
        width: 100%;
    }

	.diceimg {
		width: 150px;
		height: 150px;
	}

	.diceroller {
		padding: 10px;
		height: 50px;
		border-radius: 10px;
		background-color: rgb(14, 107, 34);
		color: white;
		font-size: 1.5rem;
		font-weight: 500;
		border: none;
	}
	.diceroller:hover {
		transform: scale(1.1);
	}
	@media (max-width: 768px) {
		.diceimg {
			width: 100px;
			height: 100px;
		}
         #controller{
	        flex-direction: column;
		 }
		 .diceroller{
			 margin: 5px;
		 }
	}
</style>
