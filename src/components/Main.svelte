<script>
  import Dashboard from "./Dashboard.svelte";
  import Settings from "./Settings.svelte";
  import History from "./History.svelte";
  import Clock from "./share/Clock.svelte";

  export let currentPage;
  export let blinds;
</script>

<main in:fade>
  <div class="wrapper">
    <h1>{currentPage}</h1>
    <div class="content-clock">
      <Clock />
    </div>
    {#if currentPage === "Dashboard"}
      <Dashboard {blinds} />
    {:else if currentPage === "Settings"}
      <Settings />
    {:else if currentPage === "History"}
      <History />
    {:else}
      <Dashboard {blinds} />
    {/if}
  </div>
</main>

<style>
  main {
    flex: 1;
    margin-left: auto;
    margin-right: auto;
  }
  .wrapper {
    max-width: 600px;
    padding: 0 1rem;
  }
  .content-clock{
    display: none;
    margin-bottom: 1rem;
  }
  @media screen and (min-width: 769px) {
    .content-clock {
      display: block !important;
    }
  }
</style>
