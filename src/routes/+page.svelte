<script>
	import Header from './Header.svelte';
	let text = $state('This is so amazing!');
	let name = $state('Magnus');
</script>

<Header {name} {text}></Header>
