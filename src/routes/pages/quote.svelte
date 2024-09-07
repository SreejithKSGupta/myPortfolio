<script lang="ts">
	const quote1 = `If the universe was a Language,`;
	const quote2 = ' Mathematics is the Alphabet,';
	const quote3 = ' Physics is the Grammar,';
	const quote4 = ' and Engineers are the authors of Epics.';
	const quoter = `-Me`;
	const quoterInfo = 'When I become famous';
</script>

<div class="quote-box">
	<div class="quote-item">
		<blockquote class="quote-text">
			{quote1}<span class="highlight">{quote2}</span>{quote3}
			<span class="highlight"> {quote4}</span>
		</blockquote>
		<cite class="quote-author">&mdash;{quoter}<br /><em>{quoterInfo}</em></cite>
	</div>
</div>

<style>
	:root {
		--quote-border-color: #449e97;
		--quote-text-color: #449e97;
		--quote-highlight-color: #ffffff;
		--quote-author-color: #ffffff;
	}

	/* Global styles */
	.quote-box {
		display: flex;
		justify-content: center;
		margin: 30px;
		padding: 20px;
		border-radius: 15px;
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
	}

	.quote-item {
		font-family: 'Barlow Condensed', sans-serif, Arial, sans-serif;
		width: 60%;
		text-align: center;
	}

	.quote-text {
		font-family: 'Abril Fatface', cursive, serif;
		color: var(--quote-text-color);
		font-size: 2rem;
		font-weight: bold;
		line-height: 1.5;
		margin: 0;
		padding: 25px;
		border: 2px solid var(--quote-border-color);
		border-radius: 20px;
	}

	.highlight {
		color: var(--quote-highlight-color);
	}

	.quote-author {
		color: var(--quote-author-color);
		font-size: 1.5rem;
		font-weight: 400;
		padding-top: 15px;
		display: block;
	}

	/* Responsive adjustments */
	@media (max-width: 768px) {
		.quote-box {
			margin: 5px;
            padding: 10px;
		}
		.quote-item {
			width: 90%;
		}

		.quote-text {
			font-size: 1.2rem;
		}

		.quote-author {
			font-size: 0.8rem;
		}
	}
</style>
