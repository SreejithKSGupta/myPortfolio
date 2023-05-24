<script lang="ts">
  // @ts-nocheck
	let projectlist = [
		[
			'Home',
			'Fully customisable browser homepage',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']

		],
		[
			'Home',
			'Fully customisable browser homepage with 0 Ads 0 restrictions  and 100% Fun, and also, it syncs across all your devices to give you a uniform experience',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']
		],	[
			'Home',
			'Fully customisable browser homepage with 0 Ads 0 restrictions  and 100% Fun, and also, it syncs across all your devices to give you a uniform experience',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']
		],
		[
			'Home',
			'Fully customisable browser homepage with 0 Ads 0 restrictions  and 100% Fun, and also, it syncs across all your devices to give you a uniform experience',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']
		],
		[
			'Home',
			'Fully customisable browser homepage with 0 Ads 0 restrictions  and 100% Fun, and also, it syncs across all your devices to give you a uniform experience',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']
		],
		[
			'Home',
			'Fully customisable browser homepage with 0 Ads 0 restrictions  and 100% Fun, and also, it syncs across all your devices to give you a uniform experience',
			'https://picsum.photos/200/300',
			'https://home5559.web.app',
			'https://github.com/sreejithks/home5559',
			['Sign in with google', 'Fully Customisable', 'Sync across devices','No Ads']
		]
	];
</script>

<div id="projects">

{#each projectlist as project}
<div class="projectitem">
    <img class="projectimg" src={project[2]} alt={project[0]} />
    <div class="projectdetails">
        <h4>{project[0]}</h4>
        <p>{project[1]}</p>
        <ul>
        {#each project[5] as features}
                <li>{features}</li>
        {/each}
    </ul>
        <div class="btnrow">
        {#if project[4]!=''}	<a href={project[4]}><div class="githubbtn" style="background-color: green;">Github</div></a>{/if}
        {#if project[3]!=''}	<a href={project[3]}><div class="livebtn" style="background-color: blue;">Live</div></a>{/if}
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
    width:clamp(400px, 40vw, 500px);
    height: 40vh;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content:space-evenly;
    background-color: #1a1a1a;
    border-radius: 10px;
    color: #ffffff;
    transition: all 0.5s ease;
    margin: 20px;
}
.projectitem:hover {
    transform: scale(1.3);
    box-shadow: 100vw 200vw 100vw 100vw rgba(0,0,0,0.75);
    -webkit-box-shadow: 0 0 100vw 100vw rgba(0,0,0,0.75);
}
.projectimg{
    width: 30%;
    border-radius: 10px;
}
.projectdetails{
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: space-evenly;
    width: 50%;
    height: 80%;
}
.projectdetails h4 {
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
    justify-content: space-around;
    width: 100%;
    height: 10%;
}
.githubbtn,
.livebtn {
    width: 120%;
    text-align: center;
    background-color: #292929;
    border-radius: 10px;
    color: #ffffff;
    text-decoration: none;
    transition: all 0.5s ease;
    padding:8px 15px;
    font-weight: bolder;
    
}
.githubbtn:hover,
.livebtn:hover {
    transform: scale(1.1);
}
a{
    text-decoration: none;
}

@media only screen and (max-width: 600px) {
		.projectitem{
            height:50vh;
            flex-direction: column;
            justify-content: space-evenly;
            padding: 20px;
        }
        .projectitem:hover {
            transform: scale(1.1);
        }
        .projectimg{
            height: 50%;
        }
        .projectdetails{
            width: 100%;
            height: 50%;
        }
	}

</style>