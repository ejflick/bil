<script>
    import Bill from './Bill.svelte';
    import { Container, Table } from 'sveltestrap';

	export let bills;
	
	function dateFormat(date) {
		return new Intl.DateTimeFormat('en-US').format(date);
	}
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
				<tr>
					<td>{bill.name}</td>
					<td>{dateFormat(bill.start)}</td>
					<td>{dateFormat(bill.end)}</td>
					<td>{bill.amount}</td>
				</tr>
			{/each}
		</tbody>
	</Table>
</Container>