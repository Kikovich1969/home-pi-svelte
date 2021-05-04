<script>
	import Header from './components/Header.svelte';
	import Main from './components/Main.svelte';
	import Footer from './components/Footer.svelte';
	
	let year = new Date().getFullYear();
	let title = 'Dashboard';

	const setTitle = e => { title = e.detail.target.innerText; }
</script>

<svelte:head>
	<title>Home Pi | {title}</title>
</svelte:head>

<Header on:setTitle={setTitle} />
<Main />
<Footer {year} />