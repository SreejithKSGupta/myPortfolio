<script lang="ts">
	import logo from '../res/sreejith.webp';

	let screenSize = 0;
	let menushow = false;
	const navlist = [
		{ href: '#herocontainer', label: 'Home' },
		{ href: '#projects', label: 'Projects' },
		{ href: '#aboutme', label: 'About' },
		{ href: '#contactme', label: 'Contact' },
		{ href: '#game', label: 'Game' }
	];
	const appname = 'My Portfolio';

	function togglemenu() {
		menushow = !menushow;
	}
</script>

<svelte:window bind:innerWidth={screenSize} />

<header class="header">
	<img id="mainlogo" src={logo} alt="logo" />
	<h1 id="headertitle">{appname}</h1>
	<nav class="headernav {screenSize < 800 ? 'mobile' : ''}" style="display:{screenSize < 800 && !menushow ? 'none' : 'flex'}">
		{#each navlist as { href, label }}
			<a href={href} on:click={() => { if (screenSize < 800) togglemenu(); }}>{label}</a>
		{/each}
	</nav>
	{#if screenSize < 800}
		<button class="hamburger" on:click={togglemenu}>
			{menushow ? '×' : '≡'}
		</button>
	{/if}
</header>

<style>
	.header {
		width: 100vw;
		height: 10vh;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #25072ce3;
		color: #fff;
		padding: 10px;
		position: relative;
	}
	#mainlogo {
		width: 8vh;
		height: 8vh;
		border-radius: 50%;
		object-fit: cover;
	}
	#headertitle {
		font-size: 2rem;
		color: rgb(0, 219, 190);
		font-weight: bold;
		font-style: oblique;
		position: absolute;
		left: 50%;
		transform: translateX(-50%);
	}
	.headernav {
		display: flex;
		gap: 10px;
		align-items: center;
	}
	.hamburger {
		background-color: transparent;
		color: #ffffff;
		font-size: 1.5rem;
		border: none;
		padding: 10px;
		cursor: pointer;
	}
	.headernav a {
		color: #ffffff;
		text-decoration: none;
		font-size: 1rem;
	}
	.headernav a:hover {
		color: #075153;
	}

	@media (max-width: 600px) {
		.headernav.mobile {
			position: absolute;
			top: 10vh;
			right: 0;
			flex-direction: column;
			background-color: rgba(8, 112, 103, 0.863);
			border-radius: 10px 0 0 10px;
			z-index: 5;
			width: 50vw;
		}
		#headertitle {
			font-size: 1.5rem;
		}
		.headernav.mobile a {
			font-size: 1.5rem;
			font-weight: bold;
			padding: 15px;
		}
	}
</style>
