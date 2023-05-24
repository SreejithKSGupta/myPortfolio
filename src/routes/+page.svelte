<script>
	import Hero from './pages/hero.svelte';
	import Header from './pages/header.svelte';
	import Footer from './pages/footer.svelte';
	import Projects from './pages/projects.svelte';
	import AboutMe from './pages/aboutme.svelte';
	import ContactMe from './pages/contactme.svelte';
	import Game from './pages/Game.svelte';
	import Quote from './pages/quote.svelte';
    export const prerender = true;
</script>

<Header />
<Hero />
<Quote />
<AboutMe />
<Projects />
<Game />
<ContactMe />
<Footer />
