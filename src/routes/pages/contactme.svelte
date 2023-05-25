<script lang="ts">
	let contactlist = [
		['tel:+917025692254', 'Phone', 'https://phone.com', '#000044'],
		['https://wa.me/7025692254', 'Whatsapp', 'https://whatsapp.com', 'green'],
		['https://t.me/7025692254', 'Telegram', 'https://telegram.com', 'blue'],
		['https://mail.to/sreejithksgupta2255@gmail.com', 'Email', 'https://mail.google.com', '#690101']
	];
	function getFavicon(websiteUrl: String): string {
		let faviconurl = 'https://www.google.com/s2/favicons?sz=256&domain=' + websiteUrl + '&size=150';
		return faviconurl;
	}
</script>

<div id="contactme">
	<h3>Contact me</h3>
	{#each contactlist as contactitem}
		<div class="contactitem" style="background-color: {contactitem[3]};">
			<a href={contactitem[0]}
				><img
					class="contactimg"
					src={getFavicon(contactitem[2])}
					alt={contactitem[1]}
				/>{contactitem[1]}</a
			>
		</div>
	{/each}
</div>

<style>
	#contactme {
		width: 70vw;
		background-color: #292929;
		border-radius: 10px;
		transition: all 0.5s ease;
		margin: 20px;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-evenly;
		align-items: center;
	}
	#contactme h3 {
		color: aliceblue;
		text-align: center;
		font-size: 160%;
	}
	.contactitem {
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		padding: 15px;
		border-radius: 10px;
		margin: 10px;
	}
	.contactitem:hover {
		scale: 1.1;
		background-color: rgb(9, 70, 49);
	}
	.contactimg {
		width: 20px;
		height: 20px;
		margin-right: 10px;
	}
	.contactitem a {
		text-decoration: none;
		color: #ffffff;
	}

	@media only screen and (max-width: 600px) {
		#contactme {
			width: 90vw;
			flex-direction: column;
		}
		.contactitem {
			width: 70%;
		}
	}
</style>
