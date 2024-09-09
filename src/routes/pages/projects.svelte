<script lang="ts">
	// @ts-nocheck
	import Modal from './Modal.svelte';
	import home from '../res/projects/home5559.webp';
	import chatsystem from '../res/projects/chat.webp';
	import facematch from '../res/projects/face_matcher.webp';
	import fastfinger from '../res/projects/fastfingers.webp';
	import weather from '../res/projects/weather.webp';
	import todo from '../res/projects/todoflutter.webp';
	import bmicalc from '../res/projects/bmicalculator.webp';
	import memmorymaster from '../res/projects/memmorymaster.webp';
	import mytimer from '../res/projects/mytimer.webp';
	import mybooks from '../res/projects/mybooks.webp';
	import elements from '../res/projects/elements.webp';
	import ceaserCipher from  '../res/projects/ceaser.webp';

	let projectlist = [
		[
			"Elements",
			'A simple and elegant Periodic table with extra features to help you visualize and understand in new ways',
			    elements,
            'https://github.com/SreejithKSGupta/elements',
            'https://elements-mu.vercel.app/',
            ['View 3D Bhors Model of Atoms', 'Color Coded','ability to see various series', 'sorting options']
		],
		[
			"Ceaser Cipher Toolkit",
			'A simple webapp that helps you decode and encode ceaser ciphers',
			    ceaserCipher,
            'https://github.com/SreejithKSGupta/ceasercipher',
            'https://ceasercipher.vercel.app/',
            ['encode ceaser ciphers', 'decode ceaser ciphers','svelte', 'vercel']
		],
		[
			'Offline Document Chat System',
			'A fully provate and offline LLM  chat system for Thrissur Police Department, as part of our college project.',
			 chatsystem,
			'https://github.com/SreejithKSGupta',
			'https://photomatcher-kappa.vercel.app/',
			['Changable Models', 'Fully Private','Based on Private GPT', 'optimized to work on lower hardwre devices','Website not available since it is offline software' ]
		],
		[
			'Face Matcher',
			'Just a Simple webapp for matching Faces to a set of uploaded images.',
			 facematch,
			'https://github.com/SreejithKSGupta/photomatcher',
			'https://photomatcher-kappa.vercel.app/',
			['Changable Models', 'Fully Private','Based on Private GPT', ]
		],
		[
			'Home',
			'WebApp meant to replace your default browser homepage, with a more customizable and user friendly version that syncs across devices.',
			 home,
			'https://github.com/SreejithKSGupta/homepage5',
			'https://home5559.vercel.app',
			['Sveltekit,', 'Firebase', 'Fully Customisable', 'Sync across devices', ]
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

  let selectedProject = null; 
  let modalVisible = false; 

  function openModal(project) {
    selectedProject = project;
    modalVisible = true;
  }

  function closeModal() {
    modalVisible = false;
    selectedProject = null;
  }
</script>

<div id="projects">
  {#each projectlist as project}
    <div class="project-item" role="button" tabindex="0" on:click={() => openModal(project)} on:keydown={(e) => e.key === 'Enter' ? openModal(project) : null}>
      <img class="project-img" src={project[2]} alt={project[0]} />
      <div class="project-details">
        <h4>{project[0]}</h4>
        <p>{project[1]}</p>
        <ul>
          {#each project[5] as feature}
            <li>{feature}</li>
          {/each}
        </ul>
        <div class="btn-row">
          {#if project[3] != ''}
            <a href={project[3]} class="project-btn github-btn" target="_blank">GitHub</a>
          {/if}
          {#if project[4] != ''}
            <a href={project[4]} class="project-btn live-btn" target="_blank">Live</a>
          {/if}
        </div>
      </div>
    </div>
  {/each}
</div>

{#if modalVisible}
  <Modal project={selectedProject} visible={modalVisible} on:closeModal={closeModal} />
{/if}


<style>
	:root {
		--primary-color: #449e97;
		--secondary-color: #1a1a1a;
		--text-color: #ffffff;
		--highlight-color: lightseagreen;
		--btn-hover-scale: 1.05;
		--shadow-color: rgba(0, 0, 0, 0.2);
	}

	#projects {
		width:80vw;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
		gap: 10px;
		padding: 0px;
	}

	.project-item {
		background-color: var(--secondary-color);
		border-radius: 10px;
		padding: 20px;
		margin: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
		box-shadow: 0 4px 8px var(--shadow-color);
		transition: transform 0.3s ease, box-shadow 0.3s ease;
	}

	.project-item:hover {
		transform: scale(1.03);
		box-shadow: 0 6px 12px var(--shadow-color);
	}

	.project-img {
		width: 100%;
		border-radius: 10px;
		height:200px;
		object-fit: cover;
		margin-bottom: 15px;
	}

	.project-details {
		text-align: center;
		color: var(--text-color);
	}

	h4 {
		color: var(--highlight-color);
		font-size: 1.5rem;
		margin-bottom: 10px;
	}

	p {
		font-size: 1rem;
		margin-bottom: 10px;
	}

	ul {
		padding-left: 0;
		list-style: none;
		margin-bottom: 15px;
	}

	li {
		font-size: 0.9rem;
		color: lightgray;
	}

	.btn-row {
		display: flex;
		justify-content: center;
		gap: 15px;
	}

	.project-btn {
		text-decoration: none;
		font-weight: bold;
		padding: 8px 20px;
		border-radius: 5px;
		color: var(--text-color);
		transition: transform 0.3s ease;
	}

	.github-btn {
		background-color: green;
	}

	.live-btn {
		background-color: blue;
	}

	.project-btn:hover {
		transform: scale(var(--btn-hover-scale));
	}

	/* Responsive Styles */
	@media (max-width: 768px) {
		h4 {
			font-size: 1.3rem;
		}

		p {
			font-size: 0.9rem;
		}

		.project-img {
			margin-bottom: 10px;
		}

		.project-btn {
			font-size: 0.9rem;
		}
		#projects {
			width:98vw;
		}
		.project-item {
		padding: 10px;
		align-items: center;
	}

	}
</style>
