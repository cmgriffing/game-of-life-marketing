<script>
	import { onMount } from 'svelte';
	import axios from 'axios';

	let scores = []
	onMount(async () => {
		const result = await axios.get('http://localhost:3100/prod/get-high-scores');
		console.log({result});
		scores = result.data.scores;
	});

</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<table class="table is-fullwidth">
	<thead>
		<tr>
			<th>Name</th>
			<th>Steps</th>
			<th>Active</th>
			<th>Preview</th>
		</tr>
	</thead>
	<tbody>
		{#each scores as score}
			<tr>
				<td></td>
				<td>{score.step_count}</td>
				<td>{score.active_count}</td>
				<td></td>
			</tr>
		{/each}
	</tbody>

</table>