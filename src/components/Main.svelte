<script>
  import Clock from "./share/Clock.svelte";
</script>

<main>
  <h1>Dashboard</h1>
  <Clock />
</main>

<style>
  main {
    flex: 1;
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
