<script lang="ts">
	import Header from './Header.svelte';
	let text = $state('This is so amazing!');
	let name = $state('Magnus');

	let status: 'OPEN' | 'CLOSED' = $state('OPEN');
</script>

<Header {name} {text}></Header>

<input type="text" bind:value={name} />
<input type="text" bind:value={text} />

<p>The store is now {status}</p>
<button
	class="btn button bg-gray-400 border p-3 rounded-md"
	onclick={() => (status = status === 'OPEN' ? 'CLOSED' : 'OPEN')}>Toggle Status</button
>
