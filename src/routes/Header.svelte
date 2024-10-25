<script lang="ts">
	import type { Snippet } from 'svelte';

	let {
		name,
		children,
		secondChild
	}: {
		name: string;
		children: Snippet;
		secondChild: Snippet;
	} = $props();
</script>

<div>
	{#if name}
		<h1>{name}'s form</h1>
	{/if}

	<h2>{name ? name : 'User'}'s form too!'</h2>

	{@render children()}

	<h3>{@render secondChild('Magnus')}</h3>
</div>

<style>
	div {
		font-size: xx-large;
	}
</style>
