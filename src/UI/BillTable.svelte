<script>
    import Bill from './Bill.svelte';
    import { Container, Table } from 'sveltestrap';

    export let bills;
</script>

<Container>
	<Table striped>
		<thead>
			<th>Name</th>
			<th>Start date</th>
			<th>End date</th>
			<th>Amount</th>
		</thead>
		<tbody>
			{#each bills as bill}
				<Bill {...bill} />
			{/each}
		</tbody>
	</Table>
</Container>