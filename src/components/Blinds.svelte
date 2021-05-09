<script>
  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";
  import { each } from "svelte/internal";

  let blinds = [
    {
      id: 1,
      room: "Gästezimmer",
      dim: 64,
      power: 0.6,
    },
    {
      id: 2,
      room: "Schlafzimmer",
      dim: 80,
      power: 0.6,
    },
    {
      id: 3,
      room: "Arbeitszimmer",
      dim: 75,
      power: 0,
    },
  ];

  let visible = false;

  let toggleSetting = () => {
    console.log("Toggle Settings");
    visible = !visible;
  };
</script>

<div id="blinds">
  {#each blinds as blind}
    <div class="blind" on:click={toggleSetting}>
      {#if blind.dim === 0}
        <img src="/img/blinds-0.svg" alt="Rollo Gästezimmer" />
      {:else if blind.dim > 0 && blind.dim <= 25}
        <img src="/img/blinds-25.svg" alt="Rollo Gästezimmer" />
      {:else if blind.dim > 25 && blind.dim <= 50}
        <img src="/img/blinds-50.svg" alt="Rollo Gästezimmer" />
      {:else if blind.dim > 50 && blind.dim <= 75}
        <img src="/img/blinds-75.svg" alt="Rollo Gästezimmer" />
      {:else}
        <img src="/img/blinds-100.svg" alt="Rollo Gästezimmer" />
      {/if}
    </div>
  {/each}
</div>
{#if visible}
  <div id="blind-settings" in:fade>
    <h3>Arbeitszimmer</h3>
    <div class="blind-controls">
      <p>
        Dim 100 <img class="icon" src="/img/percentage-solid.svg" width="9" alt="Percent" />
      </p>
      <p>
        0.6 Watt <img class="icon" src="/img/plug-solid.svg" width="9" alt="Plug" />
      </p>
      <section class="blind-buttons">
        <Button label="Open" />
        <Button label="Close" />
        <Button label="Set" />
      </section>
    </div>
    <div class="blind-slider">
      <input step="10" min="0" max="100" value="0" type="range" />
    </div>
  </div>
{/if}
<div class="bracket">
  <Button icon="lock_open" additionalStyles="position: relative; top: 10px;" />
</div>

<style>
  #blinds {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    width: 100%;
  }
  .blind {
    width: 31%;
    background-color: #4a4a4a;
    padding: 0.7rem;
    margin-bottom: 0.5rem;
    border-radius: 6px;
    cursor: pointer;
  }
  .blind img {
    width: 100%;
  }
  #blind-settings {
    background-color: #fff;
    border-radius: 6px;
    color: #4a4a4a;
    padding: 0.3rem 1rem;
  }
  #blind-settings h3 {
    font-weight: 300;
  }
  .blind-controls {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.9rem;
    font-weight: 300;
  }
  .blind-slider {
    margin: 0.5rem 0;
  }
  .blind-slider input {
    width: 100%;
  }
  .blind-buttons {
    display: flex;
    flex-basis: 40%;
    justify-content: space-between;
  }
  .icon {
    display: inline-block;
  }
  .bracket {
    border-left: 1px solid white;
    border-right: 1px solid white;
    border-bottom: 1px solid white;
    width: 70%;
    margin: 0.2rem auto 1rem auto;
    text-align: center;
    max-height: 30px;
  }
  .bracket div {
    position: relative;
    bottom: -10px;
  }
</style>
