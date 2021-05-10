<script>
  import { fade } from "svelte/transition";
  import Divider from "./share/Divider.svelte";
  import Blinds from "./Blinds.svelte";
  import Heatings from "./Heatings.svelte";

  export let blinds;
</script>

    <Divider deviderText="Markisen" />
    <Blinds {blinds} />
    <Divider deviderText="Heizungen" />
    <Heatings />

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
