<script lang="ts">
	let {
		name = 'Magnus'
	}: {
		name: string;
	} = $props();
</script>

<div>
	{#if name}
		<h1>{name}'s form</h1>
	{/if}

	<h2>{name ? name : 'User'}'s form too!'</h2>
</div>

<style>
	div {
		font-size: xx-large;
	}
</style>
