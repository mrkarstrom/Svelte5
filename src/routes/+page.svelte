<script lang="ts">
	import { error } from '@sveltejs/kit';
	import Header from './Header.svelte';

	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ''
	});
</script>

<main>
	<p>Step: {formState.step}</p>
	{#if formState.step === 0}
		<div class="">
			<label for="name">Your name</label>
			<input type="text" id="name" bind:value={formState.name} />
		</div>
	{/if}
</main>
