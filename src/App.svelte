<script type="text/javascript">
	let factors = []
	let risks = [
		{id: 'Age > 65', val: 1, done: false},
		{id: 'Age > 75', val: 1, done: false},
		{id: 'Female Sex', val: 1, done: false},
		{id: 'CHF Hx', val: 1, done: false},
		{id: 'HTN Hx', val: 1, done: false},
		{id: 'Prior Stroke', val: 2, done: false},
		{id: 'Prior MI/PAD', val: 1, done: false},
		{id: 'Diabetes Hx', val: 1, done: false},
	]
	let elements = 0
	
	$: selected = risks.filter(t => t.done)

	$: sumS = selected.reduce((s,a) => s + a.val, 0);

</script>

<main>

	<h1>CHA2DS2VASc</h1>
	{#each risks as risk (risk)}
	<label>
		<input name="riskfactor" type="checkbox" bind:checked={risk.done}> 
		{risk.id} 
		<br>
	</label>	
	
	{/each}
	<p style="font-size:50px">CHA2DSVASc SCORE: {sumS}</p>


</main>

<style>

</style>