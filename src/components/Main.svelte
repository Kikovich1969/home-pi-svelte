<script>
  import Dashboard from './Dashboard.svelte';
  import Settings from './Settings.svelte';
  import History from './History.svelte';
  
  export let currentPage;
  export let blinds;
</script>

{#if currentPage === 'Dashboard'}
<Dashboard {blinds} />
{:else if currentPage === 'Settings'}
<Settings />
{:else if currentPage === 'History'}
<History />
{:else}
<Dashboard {blinds} />
{/if}

<style>
  
</style>
