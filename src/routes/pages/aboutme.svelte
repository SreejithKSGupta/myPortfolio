<script lang="ts">
	import Masonry from '../components/masonary.svelte';

	let items = [
		{
			title: 'About Me',
			content: `Hey there! I'm Sreejith KS, Just completed my Computer Science and Engineering degree at Government Engineering College Thrissur. 
			I love having a surface-level understanding of many topics, but I also dive deep into a few that really captivate me. I'm all about practicality, 
			efficiency, and simple designs that work! That's me in a nutshell.`
		},
		{
			title: 'Education',
			content: `Bachelor of Technology (B.Tech) in Computer Science Engineering, Government Engineering College Thrissur, Kerala (Year of Completion: 2024). 
			Also completed my Higher Secondary Education at HSS Sreekrishnapuram, Kerala (2019), and Secondary Education at Jawahar Navodaya Vidyalaya Palakkad, Kerala (2017).`
		},
		{
			title: 'My Hobbies',
			content: `I'm passionate about technology, including laptops, mobile phones, and Android customization. I also enjoy DIY projects, films, series, paleontology, and theoretical physics. 
			I run a tech website and keep myself updated on all things tech!`
		},
		{
			title: 'My Experience',
			content: `During college, I was the IEEE Chapter Webmaster and part of the team that built the alumni website for my school. I also run a reasonably successful tech website with a friend, which has helped me gain web development experience. Additionally, I completed two freelance projects.`
		},
		{
			title: 'Projects',
			content: `I focus on building user-friendly websites and apps with Svelte, CSS, and JavaScript. I also develop native apps with Flutter. One of my most notable projects is "Homepage," a customizable web tool solving a personal problem I faced while browsing.`
		},
		{
			title: 'Goals',
			content: `I aim to be a skilled programmer and a good human being, making a positive impact through technology. My goal is to transform my passion into a fulfilling career.`
		},
		{
			title: 'Where I See Myself in 10 Years',
			content: `In 10 years, I see myself as a versatile professional in computer science, most likely in web/app development. But I'm always open to exploring new fields in this ever-evolving domain.`
		},
	];
</script>

<div id="aboutme" class="cardbox">
	<h1 id="aboutmeheading">All About Me</h1>
	<Masonry>
		{#each items as item, index}
			<div class="aboutitem">
				<h2 class="subheading">{item.title}</h2>
				<p>{item.content}</p>
			</div>
		{/each}
	</Masonry>
</div>

<style>
	:root {
		--main-bg-color: #ac1f1f;
		--main-text-color: #ffffff;
		--highlight-color: rgb(247, 179, 77);
		--gradient-bg-hover: linear-gradient(160deg, #004268 0%, #04685c 100%);
		--default-bg: linear-gradient(135deg, #385669 0%, #373a75 100%);
		--hover-bg: linear-gradient(160deg, #004268 0%, #04685c 100%);
	}

	.cardbox {
		width: 80vw;
		background-color: var(--main-bg-color);
		color: var(--main-text-color);
		border-radius: 15px;
		box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.3);
		margin: 100px 0px;
		padding: 30px;
		transition: all 0.3s ease;
	}

	#aboutmeheading {
		text-align: center;
		font-size: 3.5rem;
		color: var(--highlight-color);
		animation: fadeInDown 1s ease;
	}

	.aboutitem {
		border-radius: 15px;
		font-size: 1.2rem;
		padding: 20px;
		background: var(--default-bg);
		transition: transform 0.5s ease, background-color 0.5s ease;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
		cursor: pointer;
	}

	.aboutitem:hover {
		transform: scale(1.05);
		background: var(--hover-bg);
	}

	.subheading {
		text-align: center;
		font-size: 1.6rem;
		color: aquamarine;
		padding: 10px;
	}

	@media screen and (max-width: 600px) {
		.cardbox {
			width: 98vw;
			margin: 0px;
			padding: 5px;
		}

		#aboutmeheading {
			font-size: 2.8rem;
		}

		.aboutitem {
			font-size: 1rem;
			padding: 10px;
			margin: 0px;
		}

		.subheading {
			font-size: 1.4rem;
		}
	}

	@keyframes fadeInDown {
		from {
			opacity: 0;
			transform: translateY(-50px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
</style>
