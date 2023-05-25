<script lang="ts">
	let quote1 = ` If the universe was a Language,`;
	let quote2 = ' Mathematics is the Alphabet,';
	let quote3 = ' Physics is the Grammar,';
	let quote4 = ' and Engineers are the authors of Epics.';
	let quoter = `-Me`;
	let quoterinfo = 'When I become famous';
</script>

<div class="QuoteBox">
	<div class="Quoteitem">
		<div class="h2">
			{quote1}<span style="color:#ffffff">{quote2}</span>{quote3}
			<span style="color:#ffffff"> {quote4}</span>
		</div>
		<div class="h3">&mdash;{quoter}<br /><em>{quoterinfo}</em></div>
	</div>
</div>

<style>
	.QuoteBox {
		display: flex;
		width: 100%;
		margin: 30px;
		justify-content: center;
	}

	.Quoteitem {
		font-family: 'Barlow Condensed', sans-serif;
		width: 50%;
		align-self: center;
	}

	.Quoteitem .h2 {
		font-family: 'Abril Fatface', cursive;
		position: relative;
		color: #449e97;
		font-size: 2rem;
		font-weight: bold;
		line-height: 1.5;
		margin: 0;
		border: 2px solid #fff;
		border: solid 2px;
		border-radius: 20px;
		padding: 25px;
	}

	.Quoteitem .h3 {
		color: #ffffff;
		font-size: 1.5rem;
		font-weight: 400;
		line-height: 1.2;
		padding-top: 15px;
		z-index: 1;
		text-align: right;
	}

	@media (max-width: 768px) {
		.Quoteitem {
			width: 80%;
		}

		.Quoteitem .h2 {
			font-size: 1.5rem;
		}
		.Quoteitem .h3 {
			font-size: 1rem;
		}
	}
</style>
