

<script>
    import SvelteSeo from 'svelte-seo';
    import HeaderImg from './res/hariwithparents.webp'
</script>


<SvelteSeo
	title="Sreejith KS Poftfolio"
	description="Hi, Im Sreejith KS, a Computer Science and engineering Student of Goverment Engineering College, this is my portfolio website"
	keywords="sreejith ks, portfolio website, student portfolio website, sreejith, sreejith github"
    canonical='https://myportfolio-8fi.pages.dev/'
    applicationName='Portfolio of sreejith'
    themeColor= #cc5555
    


    	openGraph={{
		title:"Sreejith KS Poftfolio",
		description: "Hi, Im Sreejith KS, a Computer Science and engineering Student of Goverment Engineering College, this is my portfolio website",
		url: 'https://myportfolio-8fi.pages.dev/',
		type: 'website',
		images: [
			{
				url: HeaderImg,
				width: 800,
				height: 600,
				alt: 'Sreejith'
			},
			{
				url: HeaderImg,
				width: 900,
				height: 800,
				alt: 'sreejith'
			},
			{ url:  HeaderImg, alt: 'Sreejith' },
			{ url:  HeaderImg, }
		],
		site_name: 'myportfolio'
	}}
	twitter={{
		card: 'summary_large_image',
		site: '@myportfolio',
		title: 'Sreejith KS Poftfolio',
		description:"Hi, Im Sreejith KS, a Computer Science and engineering Student of Goverment Engineering College, this is my portfolio website",
		image:HeaderImg
    }}
/>