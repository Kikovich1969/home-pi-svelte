<script>
  import Dashboard from './Dashboard.svelte';
  import Settings from './Settings.svelte';
  import History from './History.svelte';
  export let currentPage;
</script>

{#if currentPage === 'Dashboard'}
<Dashboard />
{:else if currentPage === 'Settings'}
<Settings />
{:else if currentPage === 'History'}
<History />
{:else}
<Dashboard />
{/if}

<style>
  
</style>
