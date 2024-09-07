<script lang="ts">
	let contactlist = [
		['tel:+917025692254', 'Phone', 'https://phone.com', '#000044', '#000108'],
		['https://wa.me/7025692254', 'Whatsapp', 'https://whatsapp.com', 'green', '#228415'],
		['https://t.me/7025692254', 'Telegram', 'https://telegram.com', 'blue', '#0036A5'],
		['mailto:sreejithksgupta2255@gmail.com', 'Email', 'https://mail.google.com', '#690101', '#8B0800']
	];

	function getFavicon(websiteUrl: string): string {
		return `https://www.google.com/s2/favicons?sz=256&domain=${websiteUrl}&size=150`;
	}
</script>

<div id="contactme">
	<div class="header">Contact Me</div>
	{#each contactlist as contactitem}
		<a href={contactitem[0]} class="contactitem" style={`background: linear-gradient(135deg, ${contactitem[3]}, ${contactitem[4]});`} aria-label={contactitem[1]}>
			<img class="contactimg" src={getFavicon(contactitem[2])} alt={`${contactitem[1]} Icon`} />
			{contactitem[1]}
		</a>
	{/each}
</div>

<style>
	:root {
		--main-bg-color: #292929;
		--header-color: #fff;
		--header-font-size: 2rem;
		--header-font-family: 'Poppins', sans-serif;
		--contact-item-padding: 20px;
		--contact-item-margin: 10px;
		--contact-item-hover-bg: rgba(255, 255, 255, 0.1);
		--contact-img-size: 30px;
		--contact-item-radius: 15px;
		--transition-speed: 0.3s;
		--box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		--btn-hover-scale: 1.1;
	}

	#contactme {
		width: 80vw;
		background-color: var(--main-bg-color);
		border-radius: var(--contact-item-radius);
		transition: all var(--transition-speed) ease;
		margin: 20px auto;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-evenly;
		align-items: center;
		box-shadow: var(--box-shadow);
		padding: 20px;
	}

	.header {
		color: var(--header-color);
		text-align: center;
		font-size: var(--header-font-size);
		font-family: var(--header-font-family);
		width: 100%;
		margin-bottom: 20px;
	}

	.contactitem {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		padding: var(--contact-item-padding);
		border-radius: var(--contact-item-radius);
		margin: var(--contact-item-margin);
		transition: transform var(--transition-speed) ease, background-color var(--transition-speed) ease;
		box-shadow: var(--box-shadow);
		color: #fff;
		font-family: 'Poppins', sans-serif;
		font-weight: 600;
		text-decoration: none;
	}

	.contactitem:hover {
		transform: scale(var(--btn-hover-scale));
		background-color: var(--contact-item-hover-bg);
		box-shadow: 0 8px 16px rgba(0, 0, 0, 0.541);
	}

	.contactimg {
		width: var(--contact-img-size);
		height: var(--contact-img-size);
		margin-right: 15px;
		border-radius: 50%;
		transition: transform var(--transition-speed) ease;
	}

	.contactitem:hover .contactimg {
		transform: rotate(360deg);
	}

	/* Responsive Styles */
	@media only screen and (max-width: 600px) {
		#contactme {
			width: 98vw;
			flex-direction: column;
			padding: 10px;
		}
		.contactitem {
			width: 90%;
			justify-content: flex-start;
		}
	}
</style>
