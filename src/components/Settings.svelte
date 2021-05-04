<script>
  import { fade } from 'svelte/transition';
  import Clock from "./share/Clock.svelte";
</script>

<main in:fade>
  <div class="wrapper">
    <h1>Settings</h1>
    <Clock />
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
