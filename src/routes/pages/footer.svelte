<script lang="ts">
    import mainfooterlogo from "../res/sreejith.webp";
    let sociallist = [
        ["https://github.com","Github"],
        ["https://linkedin.com","Linkedin"],
        ["https://asastech.in","Asastech"],
        ["https://hackerrank.com","Hackerrank"]
    ]
    let contactlist = [
        ["tel:+917025692254","Phone","https://phone.com"],
        ["https://wa.me/7025692254","Whatsapp","https://whatsapp.com"],
        ["https://t.me/7025692254","Telegram","https://telegram.com"],
        ["https://mail.to/sreejithksgupta2255@gmail.com","Email","https://mail.google.com"]
    ]
     function getFavicon(websiteUrl:String): string {
          let faviconurl = "https://www.google.com/s2/favicons?sz=256&domain=" + websiteUrl + "&size=150";
          return faviconurl;
    }
</script>

<div class="footer">
	   <div class="footer_col">
	   			<h3>Quick Links</h3>
	   				{#each sociallist as url}
                           <div class="footerlinkitem">
                               <a href={url[0]}>
                                   <img class="footerlinkimg" src={ getFavicon(url[0])} alt={url[1]} />
                                       {url[1]}
                               </a>
                           </div>
                    {/each}
	   </div>
       <div class="footer_col">
                <h3>Contact me</h3>      
                    {#each contactlist as contactitem}
                           <div class="footerlinkitem">
                               <a href={contactitem[0]}>
                                   <img class="footerlinkimg" src={ getFavicon(contactitem[2])} alt={contactitem[1]} />
                                   {contactitem[1]}
                               </a>
                           </div>
                    {/each}
       </div>
	   		<img  class="footerlogo" src={mainfooterlogo} alt="logo" />
</div>



<style>
    h3{
        color: #00ffdd;
    }
.footer {
    width: 100vw;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    background-color: #25072ce3;
    color: #fff;
    padding: 10px;
}
.footer_col {
    width: 30%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
}
.footerlinkitem{
    display: flex;
    flex-direction: row;
    padding:5px;
}
.footerlinkitem a {
    color: #fff;
    text-decoration: none;
}
.footerlinkitem :hover{
    color: cadetblue;
}
.footerlinkimg {
    width: 25px;
    height: 25px;
    object-fit: cover;
    margin-right: 10px;
    border-radius: 50%;
}
.footerlogo {
    width: 8vw;
    height:8vw;
    object-fit: cover;
    border-radius: 50%;
}

@media only screen and (max-width: 600px) {
    .footer {
        flex-direction: column;
        align-items: center;
    }
    .footer_col {
        width:auto;
        font-size: 130%;
        margin: 10px;
    }
    .footerlogo {
        width: 20vw;
        height:20vw;
    }
}
</style>