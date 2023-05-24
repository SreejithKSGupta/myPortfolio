<script>
	import mainimg from '../res/sreejith.webp';
	const layer = 5;
	let y = 0;
	let name = 'Sreejith KS';
	let CTAtxt = 'A Computer Science Student From GEC Thrissur passionate about Tech , UI and Coding';
	let skills1 = [
		'Svelte',
		'Wordpress',
		'Flutter',
		'React',
		'HTML',
		'CSS',
		'FireBase',
		'JavaScript',
		'UI/UX'
	];
	let skills2 = [
		'Python',
		'Java',
		'C',
		'C++',
		'NodeJS',
		'GoLang',
		'MongoDB',
		'Git',
		'MySQL',
		'GitHub'
	];
</script>

<svelte:window bind:scrollY={y} />

<div id="herocontainer">
	<div id="heropart">
		<div id="herosection">
			<h2 id="herotext"
				style="transform: translate(0, {y < 2 ? y * layer/3 : -y * layer/3}px) ; opacity:{1 - y / 300}"
			>
				Hi, I'm {name}
			</h2>
			<span
				class="spanpar"
				style="transform: translate({y < 2 ? y * layer/5 : -y * layer/5}px, {y < 2
					? (y * layer) / 1.5
					: (-y * layer) / 1.5}px) ; opacity:{1 - y / 100}">{CTAtxt}</span
			>
		</div>
		<div id="herosection">
			<img class="mainimg"
				src={mainimg}
				alt="hero"
				style="transform: translate( {y < 2 ? -1 * y * layer/8 : y * layer/8}px,0) ; opacity:{1 -
					y / 300}"
			/>
			
		</div>
		<div id="skillsline">
			<div class="skillslist" style="transform: translate( {y < 2 ? -1 * y * layer/10 : y * layer/10}px,0) ; opacity:{1-y / 900}">
				{#each skills1 as skill}
				<div>{skill}</div>
				{/each}
			</div><br>
			<div class="skillslist" style="transform: translate( {y < 2 ? 1 * y * layer/10 : -1*y * layer/10}px,0) ; opacity:{1-y / 900}">
				{#each skills2 as skill}
				<div>{skill}</div>
				{/each}
			</div>

		</div>
	</div>
</div>

<style>
	#herocontainer {
		width: 100vw;
		height: 90vh;
		overflow: hidden;
		background-image: url('../res/BG.webp');
		background-repeat: no-repeat;
		background-size: cover;
	}
	#heropart {
		width: 100vw;
		height: 90vh;
		background-color: #000000c0;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		align-items: center;
	}
	#herotext{
		animation: glow 2s infinite;
	}
	#skillsline {
		width: 80%;
		height: 20%;
		display: flex;
		flex-direction: row;
		color: #fff;
		font-size: 150%;
		white-space: nowrap;
		overflow: hidden;
		display: inline-block;
		justify-content: space-evenly;
	}
	.skillslist{
		height: 30%;
		margin: 10px;
		padding: 10px;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		border-bottom: dotted 1px #fff;
		border-top: dotted 1px #fff;
	}
	.mainimg{
		width: 25vw;
		height:25vw;
		border-radius: 50%;
	}
	.skillslist :hover{
		border-bottom: dotted 1px #00ffbf;
		border-top: dotted 1px #06e6c0;
		transition: all 0.5s ease;
	}

	.skillslist div:hover{
		transform: scale3d(1.2, 1.2, 1.2);
		color: #00e1ff;
		transition: all 0.5s ease;
	}

	#herosection {
		width: 45%;
		height: 70%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		color: #fff;
		font-size: 250%;
		text-align: center;
	}
	.spanpar {
		font-size: 120%;
		color: #a8a8a8;
		width: 40vw;
	}
	.spanpar::before {
		content: 'A Computer Science Student From GEC Thrissur passionate about Tech , UI and Coding';
		position: absolute;
		top: 0;
		left: 0;
		left: 0.5px;
		animation: glitch-top 2s infinite;
	}

	@media only screen and (max-width: 600px) {

	 
		#herosection {
			width: 100%;
			height:auto;
			font-size: 150%;
		}
		#skillsline {
			width: 100%;
			height: auto;
			font-size: 60%;
			flex-wrap: wrap;
		}
		.mainimg{
			width: 30vh;
			height:30vh;
		}
		.spanpar {
			font-size: 100%;
			width: 90vw;
		}
	}

	@keyframes glitch {
		0% {
			transform: none;
		}
		20% {
			transform: skewX(-10deg) scale(1.1);
		}
		40% {
			transform: none;
		}
		60% {
			transform: skewX(5deg) scale(0.9);
		}
		80% {
			transform: none;
		}
		100% {
			transform: none;
		}
	}
	@keyframes glitch-top {
		0%,
		100% {
			transform: none;
			text-shadow: #008cffec -3px 0px, #ff0000da 3px 0px;
		}
		20% {
			transform: translateY(-1px);
		}
		40% {
			transform: translateY(-1px) translateX(-2px);
		}
		60% {
			transform: translateY(-1px);
			text-shadow: rgba(255, 0, 212, 0.808) 3px 0px, #51ff00d5 3px 0px;
		}
		80% {
			transform: translateY(-1px) translateX(2px);
		}
	}
	@keyframes glow{
		0%,100%{
			text-shadow: #b5c017 1px 3px;
		}
		50%{
			text-shadow: #17bac0 1px 3px;
		}
	}
</style>
