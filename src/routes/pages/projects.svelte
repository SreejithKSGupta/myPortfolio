<script lang="ts">
	// @ts-nocheck
	import home from '../res/projects/home5559.webp';
	import assetify from '../res/projects/assettify.webp';
	import fastfinger from '../res/projects/fastfingers.webp';
	import weather from '../res/projects/weather.webp';
	import todo from '../res/projects/todoflutter.webp';
	import bmicalc from '../res/projects/bmicalculator.webp';
	import memmorymaster from '../res/projects/memmorymaster.webp';
	import mytimer from '../res/projects/mytimer.webp';
	import mybooks from '../res/projects/mybooks.webp';
	let projectlist = [
		[
			'Home',
			'Homepage is a webApp that is meant to replace your default browser homepage, with a more customizable and user friendly version that syncs across devices.',
			 home,
			'https://github.com/SreejithKSGupta/Homepage',
			'https://home5559.web.app',
			['HTML,CSS,JS,', 'Sign in with google', 'Fully Customisable', 'Sync across devices', 'No Ads']
		],
		[
			'Assettify',
			'group project with a modern take on helping the young generations build good financial management skills, through gamification',
			 assetify,
			'https://github.com/SreejithKSGupta/AssetiFii',
			'https://assetifii.web.app/',
			['HTML,CSS,JS,', 'Sign in with google']
		],
		[
			'Fast Fingers',
			'Typing game to improve typing speed in a fun way, that rewards you for your efforts.',
			 fastfinger,
			'https://github.com/SreejithKSGupta/FastFingers',
			'https://sreejithksgupta.github.io/FastFingers/',
			['HTML,CSS,JS,']
		],
		[
			'Weather',
			'Weather app using openweathermap api, manual/automatic location slection',
			 weather,
			'https://github.com/SreejithKSGupta/weather-app',
            'https://sreejithksgupta.github.io/weather-app/',
			['HTML,CSS,JS,Open Weather Map API']
		],
		[
			'Todo',
			'Todo app using flutter, with material themes and Fluid animations',
			 todo,
			'https://github.com/SreejithKSGupta/mytodoo',
			'https://github.com/SreejithKSGupta/mytodoo/releases/download/initial/app-release.apk',
			['Flutter' ,'Material 3','Responsive', 'APK and EXE files available' ]
		],
		[
			'BMI Calculator',
			'BMI Calculator using flutter, with real time changing slider',
			 bmicalc,
			'https://github.com/SreejithKSGupta/mybmi',
			'https://github.com/SreejithKSGupta/mybmi/releases/download/initial/MyBmi.apk',
			['Flutter' ,'Material 3','real time slider', 'APK and EXE files available' ]
		],
		[
			'Memmory Master',
			'Simple card opening Game using vanilla JS, with level adjustments',
			 memmorymaster,
			'https://github.com/SreejithKSGupta/memorymaster',
			'https://sreejithksgupta.github.io/memorymaster/',
			['HTML, CSS,JS', 'Responsive', 'Level adjustments', ]
		],
		[
			'My Timer',
			'Timer app built using vanilla JS, with gamified UI that tracks the time spent and awards points',
			 mytimer,
			'https://github.com/SreejithKSGupta/Timer',
			'https://sreejithksgupta.github.io/Timer/',
			['HTML, CSS,JS' ,'colourfull UI','Gamified' ]
		],
		[
			'My Books',
			'Book finder app build using JS and google books api, with a responsive UI',
		 	 mybooks,
			'https://github.com/SreejithKSGupta/MyBooks',
			'https://sreejithksgupta.github.io/MyBooks/',
			['HTML ,CSS ,JS' ,'Material theme','Responsive', 'Google books api' ]
		],
		
	];
</script>

<div id="projects">
	{#each projectlist as project}
		<div class="projectitem">
			<img class="projectimg" src={project[2]} alt={project[0]} />
			<div class="projectdetails">
				<div class="h4">{project[0]}</div>
				<p>{project[1]}</p>
				<ul>
					{#each project[5] as features}
						<li>{features}</li>
					{/each}
				</ul>
				<div class="btnrow">
					{#if project[4] != ''}
						<a href={project[3]}
							><div class="projectbtn" style="background-color: green;">Github</div></a
						>{/if}
					{#if project[3] != ''}
						<a href={project[4]}
							><div class="projectbtn" style="background-color: blue;">Live</div></a
						>{/if}
				</div>
			</div>
		</div>
	{/each}
</div>

<style>
	#projects {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		width: 100%;
		justify-content: space-evenly;
	}
	.projectitem {
		width: clamp(400px, 40vw, 500px);
		height: 40vh;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-evenly;
		background-color: #1a1a1a;
		border-radius: 10px;
		color: #ffffff;
		transition: all 0.5s ease;
		margin: 20px;
	}
	.projectitem:hover {
		transform: scale(1.3);
		box-shadow: 100vw 200vw 100vw 100vw rgba(0, 0, 0, 0.75);
		-webkit-box-shadow: 0 0 100vw 100vw rgba(0, 0, 0, 0.75);
	}
	.projectimg {
		width: 30%;
		border-radius: 10px;
		height: auto;
	}
	.projectdetails {
		display: flex;
		flex-direction: column;
		align-items: left;
		justify-content: space-evenly;
		width: 50%;
		height: 80%;
	}
	.projectdetails .h4 {
		font-size: 1.5rem;
		text-align: center;
		color: lightseagreen;
		height: 20%;
	}
	.projectdetails p {
		font-size: 1rem;
		height: 40%;
	}
	.projectdetails ul {
		font-size: 1rem;
		height: 30%;
		padding-left: 10px;
	}
	.btnrow {
		display: flex;
		justify-content: space-evenly;
		width: 100%;
		height: 10%;
	}
	.projectbtn {
		width: 120%;
		text-align: center;
		border-radius: 10px;
		color: #ffffff;
		transition: all 0.5s ease;
		padding: 8px 15px;
		font-weight: bolder;
	}
	.projectbtn:hover {
		transform: scale(1.1);
	}
	a {
		text-decoration: none;
	}

	@media only screen and (max-width: 600px) {
		.projectitem {
			height: auto;
			flex-direction: column;
			padding: 10px;
		}
		.projectitem:hover {
			transform: scale(1.1);
			box-shadow: none;
			-webkit-box-shadow: none;
		}
		.projectimg {
			width: 50%;
			height: auto;
		}
		.projectdetails {
			width: 100%;
			height: auto;
		}
		.projectdetails ul,
		.projectdetails p {
			height: auto;
			padding: 10px;
		}
		.btnrow {
			width: 100%;
			height: auto;
		}
		.projectbtn {
			width: 25vw;
			height: auto;
		}
	}
</style>
