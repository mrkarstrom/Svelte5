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

<main class="w-screen min-h-screen flex flex-col items-center justify-center gap-2">
	<Header name="Test"></Header>
	<p>Steg: {formState.step + 1}</p>

	{@render formStep({ question: 'Vad heter du?', id: 'name', type: 'text' })}

	{#if formState.error}
		<p class="error">{formState.error}</p>
	{/if}
</main>

{#snippet formStep({ question, id, type }: { type: string; id: string; question: string })}
	<article>
		<div>
			<label for={id}>{question}</label>
			<input {type} {id} bind:value={formState[id]} />
		</div>
	</article>
{/snippet}

<style>
	.error {
		color: red;
	}
</style>
