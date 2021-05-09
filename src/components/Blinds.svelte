<script>
  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";

  let visible = false;

  let toggleSetting = () => {
    console.log("Toggle Settings");
    visible = !visible;
  };
</script>

<div id="blinds">
  <div class="blind" on:click={toggleSetting}>
    <img src="/img/blinds-0.svg" alt="Rollo Gästezimmer" />
  </div>

  <div class="blind">
    <img src="/img/blinds-1.2.svg" alt="Rollo Schlafzimmer" />
  </div>
  <div class="blind">
    <img src="/img/blinds-1.svg" alt="Rollo Arbeitszimmer" />
  </div>
</div>
{#if visible}
  <div id="blind-settings" transition:fade>
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
