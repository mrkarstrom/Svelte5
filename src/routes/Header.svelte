<script lang="ts">
	let {
		name,
		text
	}: {
		name: string;
		text: string;
	} = $props();
</script>

<h1>Hello {name}</h1>
<h1>Your secret name is {name.replace('u', '*')}</h1>
<h1>Your special name is {text.replaceAll('a', 'X')}</h1>

<style>
</style>
