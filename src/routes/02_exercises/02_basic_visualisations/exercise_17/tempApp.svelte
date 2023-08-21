<script>
	import * as d3 from 'd3';
	import {onMount} from 'svelte';
	
	let width = 400;
	let height = 4650;
	
	let data = [];
	onMount(async function() {
		data = await d3.csv('https://vega.github.io/vega-datasets/data/gapminder-health-income.csv', (d) => ({
			...d,
			income: +d.income,
			health: +d.health,
			population: +d.population
		}));
		console.log(data);
	});
	
	$: xScale = d3.scaleLinear()
		.domain([0, d3.max(data, (d) => d.health)])
		.range([0, width]);
	
	$: colorScale = d3.scaleOrdinal()
		.domain(data.map(d => d.region))
		.range(d3.schemeTableau10)
</script>

<svg {width} {height}>
	{#each data as d, i}
		<rect class="bar"
					x="0"
					y={i * 25}
					width={xScale(d.health)}
					height="25"
					fill={colorScale(d.region)} />
	
		<text class="label"
					x={xScale(d.health)}
					y={i * 25}
					dx="-5"
					dy="1.2em">
			{d.country}: {d.health}
		</text>
	{/each}
</svg>

<style>
	.bar {
		stroke: white;
	}
	
	.label {
		fill: white;
		font-size: small;
		text-anchor: end;
	}
</style>
