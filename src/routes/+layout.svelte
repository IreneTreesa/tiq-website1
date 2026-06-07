<script>
	import Menu from '../components/Menu.svelte';
	import Footer from '../components/footer.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<Menu />

<main >	{@render children()}
</main>

<Footer />
