<script>
	import { page } from '$app/stores';
</script>

<svelte:head>
	<title>{$page.status}</title>
</svelte:head>

<div>
	{#if $page.status === 404}
		<h1> Welcome,
			<button onclick="window.location.href = '/locations';">Movie locations</button>
		</h1>

	{:else}
		<h1>Something went wrong</h1>
	{/if}
</div>

<style>
	h1 {
		margin: 3.5em 0;
		text-align: center;
	}
	body{
		background-color: #f2d689;
		z-index: 1;
	}
	h1 {
		text-shadow: 2px 1px #381506 ;
		color: #12251d;
	}

	button{
		display: inline-block;
		background-color: #381506;
		border-radius: 10px;
		border: 4px  #cccccc;
		color: #eeeeee;
		text-align: center;
		font-size: 16px;
		width: 400px;
		transition: all 0.5s;
		cursor: context-menu;
		margin: 65px;
		padding: 15px;
	}
	button:hover {
		background-color: green;
	}
	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>
