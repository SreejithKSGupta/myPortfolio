<script lang="ts">
	let quote1 = `If the universe was a Language,`;
	let quote2 = ' Mathematics is the Alphabet,';
	let quote3 = ' Physics is the Grammar,';
	let quote4 = ' and Engineers are the authors of Epics.';
	let quoter = `-Me`;
	let quoterinfo = 'When I become famous';
</script>

<div class="QuoteBox">
	<div class="Quoteitem">
		<div class="h2">
			{quote1}<span class="highlight">{quote2}</span>{quote3}
			<span class="highlight"> {quote4}</span>
		</div>
		<div class="h3">&mdash;{quoter}<br /><em>{quoterinfo}</em></div>
	</div>
</div>

<style>
	:root {
		--quote-border-color: #449e97;
		--quote-text-color: #449e97;
		--quote-highlight-color: #ffffff;
		--quote-author-color: #ffffff;
	}

	.QuoteBox {
		display: flex;
		margin: 30px;
		justify-content: center;
		padding: 20px;
		border-radius: 15px;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
	}

	.Quoteitem {
		font-family: 'Barlow Condensed', sans-serif;
		width: 60%;
		align-self: center;
	}

	.Quoteitem .h2 {
		font-family: 'Abril Fatface', cursive;
		color: var(--quote-text-color);
		font-size: 2rem;
		font-weight: bold;
		line-height: 1.5;
		margin: 0;
		border: 2px solid var(--quote-border-color);
		border-radius: 20px;
		padding: 25px;
	}

	.Quoteitem .h2 .highlight {
		color: var(--quote-highlight-color);
	}

	.Quoteitem .h3 {
		color: var(--quote-author-color);
		font-size: 1.5rem;
		font-weight: 400;
		line-height: 1.2;
		padding-top: 15px;
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
