<script>
  import Clock from "./share/Clock.svelte";
  import Divider from "./share/Divider.svelte";
</script>

<main>
  <div class="wrapper">
    <h1>Dashboard</h1>
    <Clock />
    <Divider dataContent='Blinds' />
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
  }

  h1 {
    font-weight: 300;
    text-align: center;
    font-size: 2.5rem;
    color: white;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
