<script lang="ts">
	import {
		Timeline,
		TimelineItem,
		TimelineSeparator,
		TimelineDot,
		TimelineConnector,
		TimelineContent,
		TimelineOppositeContent
	} from 'svelte-vertical-timeline';
	import { fly } from 'svelte/transition';
	import Dice from '../components/dicebox.svelte';
	
	let liferoad = [
		[0, 'Just been born as Son to Ambika and Suresh K , @Palakkad'],
		[1, 'Probably started walking, which was my greatest achivement at the time'],
		[2, "Started to talk I guess, that's one thing am excellent at, even now"],
		[3, 'Managed to break a trycycle within an hour i got it, with the assistance of my brother'],
		[4, 'Started my school life at GLPS vakkada, PKD'],
		[
			5,
			'reboot of school life @ Annai Matriculation School Tirupur, as initial one failed to meet expectaions'
		],
		[6, 'My age when the only time I have been a Class first (@UKG)'],
		[7, 'learned a lesson that I will never forget'],
		[8, 'Learned to ride a Bicycle alone, without support wheels'],
		[9, 'My lifelong obesession with Cars and Bikes started, and I moved back to kerala'],
		[10, 'Finished my transition to Atheism, and wrapped my head around fractions'],
		[11, 'Became MTSE state first, after getting 3rd 2 yrs prior'],
		[12, 'Staarted my chapter @ JNV Malampuzha, for better or worse'],
		[13, 'Letters began invading numbers in my maths text book'],
		[14, 'Realised my life as an automobile engineer might not be as good as I thought'],
		[
			15,
			'Not all years have somthing note worty, It was good though, and pivoted towards Programming'
		],
		[16, 'Went to Rajasthan for a year, Met My Lifelong Best friend, and learned hindi'],
		[17, '10th turned out to be not as lifechanging as everyone made it to be.'],
		[
			18,
			'Vibing with my chunks @SKPHSS Sreekrishnapuram, got my first Phone and Laptop, addiction to tech and coding begins'
		],
		[
			19,
			"Made my lifelong friend , didn't score enough in KEAM for my dream College"
		],
		[
			20,
			'Went to entrance coaching, pretty good for a place without phone and freedom, and yeah, corona happened'
		],
		[
			21,
			'when life gives you lemon, make lemonade, if it says you are not good enough for NIT, Enjoy at GEC'
		],
		[
			22,
			'Have the best group of friends, started a website, youtube channel, and my preference for UI becomes obvious'
		],
		[
			23,
			'Finally learned Flutter, svelte, react, became IEEE webmaster for my college, and made this profile'
		],
		[
			24,
			'Finished my College, soome of the best group of memories and friends'
		],
		[27, 'might be the year I get someting important, but missing to my life'],
		[
			30,
			'Life will be great, I will be better at what I do the best, Bugatti releases their first EV'
		],
		[
			40,
			'My chindren would probably tell me, "Welcome to the future Old man!!", and regret ever opening their mouth'
		],
		[50, "Retiered, enjoying my life, and all it's beauty, Might finally buy an SLS AMG too.."],
		[
			60,
			"how long do you think let I'll Live ,eating meals 3 times a day for all my life? 120 years?"
		]
	];

	$: dicecount = 0;
	let words = ['Play it', 'Own It', 'Enjoy it'];
	let current = 0;
	let screenwidth = 0;

	setInterval(() => {
		current = current + 1 === words.length ? 0 : current + 1;
	}, 1500);
	$: dicecount && scrollToAge();

	function scrollToAge() {
		let age = document.getElementById(`timeage${dicecount}`);
		if (!age) {
			for (let i = 0; i < liferoad.length; i++) {
				if ((liferoad[i][0] as number) > dicecount) {
					dicecount = liferoad[i][0] as number;
					age = document.getElementById(`timeage${liferoad[i][0]}`);
					setagetocenter(age);

					return;
				}
			}
		} else {
			setagetocenter(age);
		}
	}
	function setagetocenter(age: HTMLElement | null) {
		age!.scrollIntoView({
			behavior: 'smooth',
			block: 'center',
			inline: 'center'
		});
	}
</script>

<svelte:window bind:innerWidth={screenwidth} />
<div id="game">
	{#if screenwidth < 600}
		<div id="gameheading">
			<h2>Life is a Game</h2>
			{#each words as word, i}
				{#if i === current}
					<div
						class="fadingwords"
						in:fly={{ y: -30, duration: 500, delay: 500 }}
						out:fly={{ y: 30, duration: 500, delay: 500 }}
					>
						...{word}
					</div>
				{/if}
			{/each}
		</div>
	{/if}
	<div class="gamebox" style="background-color: aliceblue;">
		<Timeline
			position="alternate"
			style={'border: solid 1px #dbdbdb; padding: 50px 0; border-radius: 2%;'}
		>
			{#each liferoad as life}
				<TimelineItem>
					<TimelineOppositeContent slot="opposite-content">
						<h1 class="timelineage" id="timeage{life[0]}">{life[0]}</h1>
					</TimelineOppositeContent>
					<TimelineSeparator style={'height:17vh'}>
						<TimelineDot style={'background-color: #7CbbE2; padding:8px;'} />
						<TimelineConnector />
					</TimelineSeparator>
					<TimelineContent>
						<p class="timelinecontent" id={life[0] + 'para'} style={`background-color: ${life[0] === dicecount ? 'blue' : '#222222'}`}>
							{life[1]}
						</p>
					</TimelineContent>
				</TimelineItem>
			{/each}
		</Timeline>
	</div>
	<div class="controlbox">
		{#if screenwidth > 600}
			<div id="gameheading">
				<h2>Life is a Game</h2>
				{#each words as word, i}
					{#if i === current}
						<div
							class="fadingwords"
							in:fly={{ y: -30, duration: 500, delay: 500 }}
							out:fly={{ y: 30, duration: 500, delay: 500 }}
						>
							...{word}
						</div>
					{/if}
				{/each}
			</div>
		{/if}
		<Dice bind:year={dicecount} />
	</div>
</div>

<style>
	#game {
		width: 90vw;
		background-color: #222222;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		border-radius: 10px;
		padding: 10px;
	}
	h2 {
		width: 100%;
		font-size: 4rem;
		font-weight: 500;
		text-align: center;
		margin: 20px;
		padding: 0;
		color: cornsilk;
	}
	.fadingwords {
		color: rgb(0, 255, 221);
		margin: 0;
		height: 0;
		width: 100%;
		text-align: center;
		font-size: 150%;
	}
	.gamebox {
		width: 40%;
		border-radius: 10px;
		height: 80vh;
		margin: 5vh 0px 0px 0px;
		overflow-y: scroll;
	}
	.controlbox {
		width: 40%;
		height: 80vh;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
	}
	.timelinecontent {
		font-size: 1.5rem;
		font-weight: 500;
		padding: 10px;
		color: white;
		border-radius: 10px;
	}
	@media (max-width: 768px) {
		#game {
			flex-direction: column;
			justify-content: flex-start;
			height: 90vh;
		}
		.gamebox {
			width: 90%;
			height: 40vh;
			flex-direction: column;
		}
		.controlbox {
			width: 90%;
			height: 20vh;
		}
		.timelinecontent {
			font-size: 1rem;
		}
		.timelineage {
			font-size: 1.5rem;
		}
		h2 {
			font-size: 1.5rem;
		}
	}
</style>
