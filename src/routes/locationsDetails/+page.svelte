<script>
	import {onMount} from "svelte";
	/** @type {import('./$types').PageData} */
	export let message;
	export let id;
	export let filmName;
	export let filmType;
	export let filmProducerName;
	export let filmDirectorName;
	export let address;
	export let year;
	onMount(async () => {
		const params = new URLSearchParams(window.location.search);
		id = params.get('id');
		filmName = params.get("filmName");
		filmType = params.get('filmType');
		filmProducerName = params.get('filmProducerName');
		filmDirectorName = params.get('filmDirectorName');
		address = params.get('address');
		year = params.get('year');
	});
</script>

<svelte:head>
	<title> Détails • Conduit</title>
</svelte:head>

<body>
<div class="auth-page">
	<div class="container page">
		<div class="row">
			<div class="col-md-6 offset-md-3 col-xs-12">
				<h1 class="text-xs-center">Details</h1>
				<div>
					<table>
						<tr>
							<th>Id</th>
							<th>Title</th>
							<th>Type</th>
							<th>Producer</th>
							<th>Director</th>
							<th>Address</th>
							<th>Year</th>

						</tr>
						<tr>
							<td>{id}</td>
							<td>{filmName}</td>
							<td>{filmType}</td>
							<td>{filmProducerName}</td>
							<td>{filmDirectorName}</td>
							<td>{address}</td>
							<td>{year}</td>
						</tr>
					</table>
				</div>
			</div>
		</div>
	</div>
</div>
</body>
<style>
	h1{
		text-align: center;
		padding: 14px;
		width: auto;
		height: 137px;
		margin-left: 20REM;

	}
	table {
		margin: auto;
	}
	th {
		text-align: center;
		background-color: #34cf46;
		border-spacing: 25px;
		font-weight: 900;
		border-style: groove;
		padding: 20px;
		margin: 30px;
	}
	.row {
		margin-right: 50rem;
	}
	body {
		background-color: #b6e0bb;
	}
	td {
		background-color: #E9F7EF;
		padding-right: 20px;
		padding-left: 30px;
	}
</style>