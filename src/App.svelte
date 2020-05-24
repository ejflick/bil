<script>
	import { Container, Nav, Navbar, NavbarBrand, NavItem, NavLink } from 'sveltestrap';

	import BillTable from './UI/BillTable.svelte';
	import BillInput from './UI/BillInput.svelte';

	let bills = [];

	let tenants = [
		{name: 'Eric', stayPeriod: {start: new Date(), end: new Date()}},
		{name: 'Person2', stayPeriod: {start: new Date(), end: new Date()}}
	];

	function addBill(event) {
		bills = [
			...bills,
			event.detail
		];

		console.log(bills);
	}
</script>
<Container>
	<BillInput on:addBill={addBill} />
	<BillTable {bills} />
</Container>