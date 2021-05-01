<script>
	import Header from './components/Header.svelte';
	import Main from './components/Main.svelte';
	import Footer from './components/Footer.svelte';
	let year = new Date().getFullYear();
</script>

<Header />
<Main />
<Footer {year} />