<script lang="ts">
	let {
		name
	}: {
		name: string;
	} = $props();
</script>

<div>
	<h2>{name ? name : 'User'}'s form too!'</h2>
</div>

<style>
	div {
		font-size: xx-large;
	}
</style>
