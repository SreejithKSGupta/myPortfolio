<script lang="ts">
	import logo from '../res/sreejith.webp';
	let screenSize = 0;
	let navlist = [
		['#herocontainer', 'Home'],
		['#projects', 'Projects'],
		['#aboutme', 'About'],
		['#contactme', 'Contact'],
		['#game', 'Game']
	];
	let appname = 'My Portfolio';
	let menushow = 'none';
	function togglemenu() {
		if (menushow == 'none') {
			menushow = 'flex';
		} else {
			menushow = 'none';
		}
	}
</script>

<svelte:window bind:innerWidth={screenSize} />

<div class="header">
	<img class="mainlogo" src={logo} alt="logo" />
	<h1 class="headertitle">{appname}</h1>
	{#if screenSize > 800}
		<div class="headernav">
			{#each navlist as navitem}
				<a href={navitem[0]}>{navitem[1]}</a>
			{/each}
		</div>
	{/if}
	{#if screenSize < 800}
		<button class="hamburger" on:click={togglemenu}> {menushow == 'none' ? '=' : 'x'} </button>
		<div class="headernav" style="display:{menushow}">
			{#each navlist as navitem}
				<a href={navitem[0]}>{navitem[1]}</a>
			{/each}
		</div>
	{/if}
</div>

<style>
	.header {
		width: 100vw;
		height: 10vh;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		background-color: #25072ce3;
		color: #fff;
		padding: 10px;
	}
	.mainlogo {
		width: 8vh;
		height: 8vh;
		border-radius: 50%;
		object-fit: cover;
	}
	.headertitle {
		font-size: 2rem;
		color: rgb(0, 219, 190);
		padding: 10px;
		font-weight: bold;
		font-style: oblique;
	}
	.headernav {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}
	.hamburger {
		background-color: transparent;
		color: #ffffff;
		font-size: 1.5rem;
		border: none;
		padding: 10px;
	}
	.headernav a {
		padding: 10px;
		color: #ffffff;
		text-decoration: none;
	}
	.headernav a:hover {
		color: #075153;
	}

	@media only screen and (max-width: 600px) {
		.headernav {
			position: absolute;
			top: 10vh;
			flex-direction: column;
			right: 0px;
			font-size: 2rem;
			font-weight: bold;
			background-color: rgba(8, 112, 103, 0.863);
			z-index: 5;
			border-radius: 10px 0px 0px 10px;
		}
		.headertitle {
			font-size: 1.5rem;
		}
	}
</style>
