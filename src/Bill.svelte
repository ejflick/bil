<script>
	export let name;
	export let period;
	export let amount;
	
	let formattedStart = new Intl.DateTimeFormat('en-US').format(period.start);
	let formattedEnd = new Intl.DateTimeFormat('en-US').format(period.end);
</script>

<div>
	<header>
		<h1>{name}</h1>
		<h2>
			{formattedStart} - {formattedEnd}
		</h2>
		<h3>${amount}</h3>
	</header>
</div>