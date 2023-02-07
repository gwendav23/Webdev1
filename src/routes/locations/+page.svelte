<script>
	import { enhance } from '$app/forms';
	import ListErrors from '$lib/ListErrors.svelte';
	/** @type {import('./$types').PageData} */
	export let data;
	export let form;
	let message = "Hello from parent";
	function handleClick(id,filmName,filmType,filmProducerName,filmDirectorName,address,year) {
		const params = new URLSearchParams();
		params.set('id', id);
		params.set('filmName', filmName);
		params.set('filmType', filmType);
		params.set('filmProducerName', filmProducerName);
		params.set('filmDirectorName', filmDirectorName);
		params.set('address', address);
		params.set('year', year);
		window.location.href = `/locationsDetails?${params.toString()}`;
	}
</script>

<svelte:head>
	<title>Locations • Conduit</title>
</svelte:head>

<div class="auth-page">
	<div class="container page">
		<div class="row">
			<div class="col-md-6 offset-md-3 col-xs-12">
				<h1 class="text-xs-center">Locations</h1>
				{#if data.locations?.length === 0}
					<div class="article-preview">No locations here... yet.</div>
				{:else}
					<div>
						<table>
							<tr>
								<th>Title</th>
								<th>Producer</th>

							</tr>
							{#each data.locations as location}
								<tr>
									<th>{location.filmName}</th>
									<th>{location.filmProducerName}</th>
									<button on:click={() => handleClick(location._id,location.filmName,location.filmType,location.filmProducerName,location.filmDirectorName,location.address, location.year)}> + info</button>

								</tr>
							{/each}
						</table>
					</div>
				{/if}
			</div>
		</div>
	</div>
</div>

<style>
	h1{
		text-align: center;
		padding: 10px;
		width: auto;
		height: 120px;
	}
	button{
		display: inline-block;
		background-color: #34cf46 ;
		border-radius: 18px;
		border: 4px  #cccccc;
		color: #eeeeee;
		text-align: center;
		font-size: 13px;
		padding: 20px;
		width: 100px;
		transition: all 0.5s;
		cursor: context-menu;
		margin: 10px;
	}
	button:hover {
		background-color: green;
	}
	body{
		background-color: #f2d689;
		z-index: 1;
	}
	#titre_column th {
		text-align: center;
		background-color: #D4EFDF;
		border-spacing: 25px;
		font-weight: 900;
		border-style: groove;
	}
	#contenu th{
		border: 9px  ;
		font-weight: 300 ;
		color:#094d11;
		padding: 8px;
		text-align: left;
	}
	table {
		width: 100%;
	}
	th {
		background-color: #b6e0bb;
	}
</style>






