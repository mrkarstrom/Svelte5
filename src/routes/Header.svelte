<script lang="ts">
	let {
		name,
		text,
		fake_name = null
	}: {
		name: string;
		text: string;
		fake_name?: null | string;
	} = $props();
</script>

<h1>Hello {name}</h1>
<h1>Your secret name is {name.replace('u', '*')}</h1>
<h1>Your special name is {text.replaceAll(/[a-z]/gi, '*')}</h1>

<p>{fake_name}</p>

<style>
</style>
