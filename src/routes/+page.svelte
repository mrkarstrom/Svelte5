<script lang="ts">
	import Header from './Header.svelte';
	let text = $state('This is so amazing!');
	let name = $state('Magnus');
	let fullName = $derived(name + ' ' + 'Karström');
	let status: 'OPEN' | 'CLOSED' = $state('OPEN');
	let fake_name = 'Wes';

	function toggle() {
		status = status === 'OPEN' ? 'CLOSED' : 'OPEN';
	}
</script>

<div class="w-full min-h-[100vh] flex flex-col items-center justify-center gap-4">
	<Header {name} {text}></Header>

	<h2>Hello {fullName}</h2>
	<input type="text" bind:value={name} />
	<input type="text" bind:value={text} />

	<p>The store is now {status}</p>
	<button
		class="btn button bg-gray-400 border p-3 rounded-md"
		onclick={() => (status = status === 'OPEN' ? 'CLOSED' : 'OPEN')}>Toggle Status</button
	>

	<button class="btn button bg-gray-400 border p-3 rounded-md" id="btn2" onclick={toggle}
		>Button2</button
	>
	<h2>Hey {fake_name}</h2>
</div>
