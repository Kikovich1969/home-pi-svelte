<script>
	import Header from './components/Header.svelte';
	import Main from './components/Main.svelte';
	import Footer from './components/Footer.svelte';
	
	let year = new Date().getFullYear();
	let currentPage = 'Dashboard';

	const setCurrentPage = e => {
		currentPage = e.detail.srcElement.dataset.target;
	}
</script>

<svelte:head>
	<title>Home Pi | {currentPage}</title>
</svelte:head>

<Header on:setCurrentPage={setCurrentPage} />
<Main {currentPage} />
<Footer {year} />