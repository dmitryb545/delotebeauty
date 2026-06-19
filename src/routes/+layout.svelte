<script>
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	const { children } = $props();
</script>

<Header />

{@render children()}

<Footer />