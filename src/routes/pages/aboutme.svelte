<script>
import Masonry from '../components/masonary.svelte'
 
    let items = [
       {
        title:"About Me",
        content:  `Hey there! I'm Sreejith KS, a Computer Science and Engineering student at Government Engineering College Thrissur.
         I love having a surface-level understanding of many topics, but I also dive deep into a few that really captivate me. When it comes to design,
          I'm all about simplicity and elegance. I'm not easily impressed by complicated designs that only offer a tiny advantage, 
          unless they're meant for massive projects. I believe in practicality and efficiency, and I find that simple solutions often work best.
           So, you'll usually see me favoring straightforward designs that just get the job done. That's me in a nutshell!`
       },
       {
        title:"Education",
        content:`Bachelor of Technology (B.Tech) in Computer Science Engineering, Government Engineering College Thrissur, Kerala (Year of Completion: 2024) , Higher Secondary Education, HSS Sreekrishnapuram, Kerala (2019)
        , Secondary Education, Jawahar Navodaya Vidyalaya Palakkad, Kerala (2017). `

       },
       {
        title:'My Hobbies',
        content:`   I have a strong passion for technology, especially laptops, mobile phones, and Android customization. My portfolio's UI
         design reflects this with its material theme and focus on customizability. Cars, bikes, and a wide range of topics like DIY projects, 
         paleontology, theoretical physics, psychology, films, and series also pique my interest. I stay updated through YouTube recommendations.
         I run a WordPress website with a friend, discussing tech-related subjects and exploring affiliate marketing as a passive income opportunity.
         While I used to enjoy reading books, I now primarily rely on the internet for knowledge like most people. Although not a sports enthusiast,
        I do occasionally play football and shuttle. `
       },
   
       {
        title:'My Goals',
        content:`I want to be a good Programmer, and a good human being. I want to be able to help people use tech efficiently, and make a difference in the world.
                    I want to be able to make a living out of my passion, fulfilling both physical and emotional needs.`
       },
   
      
   
       {
        title:'Where I see Myself in 10 years',
        content:   `In 10 years, I see myself as an accomplished and versatile professional in the field of computer science engineering, Most probably in web/App designing.
                However, If someting else comes up that is more promising, which I like more, I'll Be learning that too. After all, in a rapidly evolving field like Computer science
                Change is and will be the only constant, and those who find a comfort zone won't innovate ` 
                },
 
       {
        title:"My projects",
        content:`My primary focus lies in creating apps and websites with user-friendly interfaces. I specialize in web development using Svelte, vanilla CSS, and JavaScript,
                 occasionally use React when needed too. Additionally, I have expertise in native app development using Flutter. In terms of content creation, I'm most Proud 
                 about Homepage, which i find is quite usefull, customizable, and solve an important issue that i faced while browsing the internet.
                I have a particular fondness for WordPress. I love its versatility and vast amount of plugins so that I can focous on the Content.`
       },
       {
        title:'My experience',
        content:`I have created some possibly good Apps, web apps and websites, but I am not sure if they are good enough to be called "experience", I also run a tech website, 
        with reasonable traffic, and am also  one of the WebMasters for the IEEE Chapter of our college. I have also tried My hand at freelancing, and have completed 2 projects.`
       },
       
      
 

    ]
 </script>

<div id="aboutme" class="cardbox">
    <div id="aboutmeheading"> All About Me </div>
<Masonry> 
    {#each items as item}
       <div class="aboutitem _card _padding">
        <div class="subheading">{item.title}</div>
        <p>{item.content}</p>
       </div>
    {/each}
 </Masonry>
</div>

<style>
   .cardbox {
		width: 80vw;
        height: auto;
		background-color: #292929;
		border-radius: 10px;
		box-shadow: 0 0 10px 0 #000000c0;
		align-items: center;
		color: #ffffff;
		transition: all 0.5s ease;
		margin: 100px;
	}

    #aboutmeheading{
        width: 100%;
        text-align: center;
        font-size:60px;
        color: rgb(247, 179, 77);
        padding: 20px;
    }
    .aboutitem{
        border-radius: 10px;
        font-size: 130%;
        padding:10px;
        background-color: #8BC6EC;
        background-image: linear-gradient(135deg, #385669 0%, #373a75 100%);
        transition:1s cubic-bezier(0.075, 0.82, 0.165, 1);

    }
    .aboutitem:hover{
        transform: scale(1.1);
        transition:1s cubic-bezier(0.075, 0.82, 0.165, 1);
        background-color: #0093E9;
        background-image: linear-gradient(160deg, #004268 0%, #04685c 100%);

    }
    .subheading{
        text-align: center;
        font-size: 140%;
        color: aquamarine;
        padding: 10px;
    }
    @media screen and (max-width: 600px) {
        .cardbox{
            width: 90vw;
            margin: 50px;
        }
        #aboutmeheading{
            font-size: 40px;
        }
        .aboutitem{
            font-size: 100%;
        }
        .subheading{
            font-size: 120%;
        }
    }
</style>