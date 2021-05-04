<script>
  import Clock from "./share/Clock.svelte";
  import Divider from "./share/Divider.svelte";
  import Blinds from "./Blinds.svelte";
  import Heatings from "./Heatings.svelte";
</script>

<main>
  <div class="wrapper">
    <h1>Dashboard</h1>
    <Clock />
    <Divider deviderText='Markisen' />
    <Blinds />
    <Divider deviderText='Heizungen' />
    <Heatings />
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
