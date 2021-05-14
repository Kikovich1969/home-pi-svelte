<script>
  import { onMount } from 'svelte';

  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";
  export let blinds;

  let visible = false;
  let preventTransform = true;

  let toggleSetting = (e) => {
    console.log(e.target.dataset.id);
    preventTransform = false;
    visible = !visible;
  };

</script>

<!-- <svelte:window on:resize={handleResize}/> -->

<div id="blinds">
  {#each blinds as blind (blind.id)}
    <div class="blind" data-id="{blind.id}" on:click={toggleSetting}>
      <img src="/img/frame.svg" class="frame" alt="Window">
      {#if blind.dim === 0}
        <img src="/img/blinds-0.svg" class="blind-img" alt="Rollo {blind.room}" in:fade out:fade class:no-transform={preventTransform} />
      {:else if blind.dim > 0 && blind.dim <= 30}
        <img src="/img/blinds-25.svg" class="blind-img" alt="Rollo {blind.room}" in:fade out:fade class:no-transform={preventTransform} />
      {:else if blind.dim > 30 && blind.dim <= 60}
        <img src="/img/blinds-50.svg" class="blind-img" alt="Rollo {blind.room}" in:fade out:fade class:no-transform={preventTransform} />
      {:else if blind.dim > 60 && blind.dim <= 99}
        <img src="/img/blinds-75.svg" class="blind-img" alt="Rollo {blind.room}" in:fade out:fade class:no-transform={preventTransform} />
      {:else if blind.dim === 100}
        <img src="/img/blinds-100.svg" class="blind-img" alt="Rollo {blind.room}" in:fade out:fade class:no-transform={preventTransform} />
      {/if}
    </div>
  {/each}
</div>

{#each blinds as blind (blind.id)}
  {#if visible}
    <div id="blind-settings" in:fade>
      <h3>{blind.room}</h3>
      <div class="blind-controls">
        <p>
          Dim {blind.dim}%</p>
        <p>
          {blind.power} Watt</p>
        <section class="blind-buttons">
          <Button label="Open" />
          <Button label="Close" />
          <Button label="Set" />
        </section>
      </div>
      <div class="blind-slider">
        <input step="10" min="0" max="100" bind:value="{blind.dim}" type="range" />
      </div>
    </div>
  {/if}
{/each}

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
    margin-bottom: 0.5rem;
    cursor: pointer;
    position: relative;
  }
  .blind img.blind-img {
    width: 80%;
    position: absolute;
    top: 10%;
    left: 10%;
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
  
  .bracket {
    border-left: 1px solid white;
    border-right: 1px solid white;
    border-bottom: 1px solid white;
    width: 70%;
    margin: 0.2rem auto 1rem auto;
    text-align: center;
    max-height: 30px;
  }
  .frame{
    width: 100%;
  }
  .no-transform{
    animation: none !important;
  }
</style>
