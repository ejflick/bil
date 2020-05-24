<script>
	import Bill from './Bill.svelte';
	import Tenant from './Tenant.svelte';
	
	let bills = [
		{
			name: 'Gas',
			period: {
				start: new Date(2020, 0, 1),
				end: new Date(2020, 1, 1)
			},
			amount: 30,
		},
		
		{
			name: 'Water',
			period: {
				start: new Date(2020, 3, 1),
				end: new Date(2020, 4, 1)
			},
			amount: 30,
		},
	];
	
	let tenants = [
		{name: 'Eric'},
		{name: 'Person2'}
	];
</script>

<style>
	.parent {
			display: flex;
			align-items: top;
	}

	.column {
		flex: 1
	}
</style>

<div class="parent">
	<div class="column">
		{#each bills as bill}
			<Bill {...bill} />
		{:else}
			<p>No bills found!</p>
		{/each}
	</div>
	<div class="column">
		{#each tenants as tenant}
			<Tenant {...tenant} />
		{:else}
			<p>No roommates</p>
		{/each}
	</div>
</div>

