<script lang="ts">
	let {
		name
	}: {
		name: string;
	} = $props();
</script>

<h1>Hello {name}</h1>
<h1>Your secret name is {name.replace('u', '*')}</h1>

<style>
</style>
