<script lang="ts">
	import { error } from '@sveltejs/kit';
	import Header from './Header.svelte';

	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ''
	});

	const QUESTIONS = [
		{
			question: 'Vad heter du?',
			id: 'namn',
			type: 'text'
		}
	];
</script>

<Header name={formState.name} />

<main class="w-screen min-h-screen flex flex-col items-center justify-center gap-2">
	<p>Steg: {formState.step + 1}</p>

	{#each QUESTIONS as question (question.id)}
		<h1>
			Fråga: {question.id}
		</h1>
		{@render formStep({ question: 'Vad heter du?', id: 'namn', type: 'text' })}
	{/each}

	{#snippet formStep({ question, id, type }: { type: string; id: string; question: string })}
		<article>
			<div>
				<label for={id}>{question}</label>
				<input {type} {id} bind:value={formState[id]} />
			</div>
		</article>
	{/snippet}
	{#if formState.step === 0}
		<div>
			<label for="name">Ditt namn</label>
			<input type="text" id="name" bind:value={formState.name} />
		</div>
		<button
			class="btn w-[300px] p-3 bg-green-300 border-4 border-green-400 rounded-md hover:bg-transparent"
			onclick={() => {
				if (formState.name !== '') {
					formState.step += 1;
					formState.error = '';
				} else {
					formState.error = 'Skriv in ditt namn!';
				}
			}}>Next</button
		>
	{:else if formState.step === 1}
		<div class="">
			<label for="bday">Din födelsedag</label>
			<input type="text" id="bday" bind:value={formState.birthday} />
		</div>
		<button
			class="btn w-[300px] p-3 bg-green-300 border-4 border-green-400 rounded-md hover:bg-transparent"
			onclick={() => {
				if (formState.birthday !== '') {
					formState.step += 1;
					formState.error = '';
				} else {
					formState.error = 'Skriv in din födelsedag!';
				}
			}}>Next</button
		>
	{/if}

	{#if formState.error}
		<p class="error">{formState.error}</p>
	{/if}
</main>

<style>
	.error {
		color: red;
	}
</style>
