<script>
	import Hero from './pages/hero.svelte';
	import Header from './pages/header.svelte';
	import Footer from './pages/footer.svelte';
	import Projects from './pages/projects.svelte';
	import AboutMe from './pages/aboutme.svelte';
	import ContactMe from './pages/contactme.svelte';
	import Game from './pages/Game.svelte';
	import Quote from './pages/quote.svelte';
</script>
<svelte:head>
  <!-- Basic SEO -->
  <title>My Portfolio | Sreejith's Personal Portfolio</title>
  <meta name="description" content="Welcome to Sreejith's personal portfolio. Explore my work, skills, and projects." />
  <meta name="keywords" content="Sreejith, portfolio, web development, front-end, projects, skills" />
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="canonical" href="https://my-portfolio-five-psi-49.vercel.app/" />

  <!-- Open Graph Tags for Social Media -->
  <meta property="og:title" content="My Portfolio | Sreejith's Personal Portfolio" />
  <meta property="og:description" content="Explore my web development projects, skills, and personal achievements." />
  <meta property="og:url" content="https://my-portfolio-five-psi-49.vercel.app/" />
  <meta property="og:image" content="https://my-portfolio-five-psi-49.vercel.app/sreejith.webp" />
  <meta property="og:type" content="website" />

  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="My Portfolio | Sreejith's Personal Portfolio" />
  <meta name="twitter:description" content="Explore my web development projects, skills, and personal achievements." />
  <meta name="twitter:image" content="https://my-portfolio-five-psi-49.vercel.app/sreejith.webp" />

  <!-- Favicon and Icons -->
  <link rel="icon" href="/sreejith.webp" />

  <!-- Structured Data for Schema.org (Personal Portfolio) -->
  <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Person",
      "name": "Sreejith",
      "url": "https://my-portfolio-five-psi-49.vercel.app/",
      "sameAs": [
        "https://www.linkedin.com/in/sreejith-k-s-gupta/",
        "SreejithKSGupta"
      ],
      "jobTitle": "Web Developer",
      "worksFor": {
        "@type": "Organization",
        "name": "Freelance"
      },
      "image": "https://my-portfolio-five-psi-49.vercel.app/sreejith.webp",
      "description": "Web Developer skilled in front-end technologies, building modern, responsive websites and apps."
    }
  </script>
</svelte:head>

<div id="content">
<Header />
<Hero />
<Quote />
<AboutMe />
<Projects />
<Game />
<ContactMe />
<Footer />
</div>

<style >
	#content {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
</style>