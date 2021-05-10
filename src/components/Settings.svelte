<script>
  import { fade } from "svelte/transition";
  import Button from "./share/Button.svelte";
</script>

    <Button icon="save" size="large" />
    <Button label="Save" icon="save" fullWidth size="small" />

<style>
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
