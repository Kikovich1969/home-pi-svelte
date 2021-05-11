<script>
  import { onMount } from 'svelte';

  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";
  export let blinds;

  let visible = false;
  let width = '';
  let height = '';

  /* onMount(() => {
    width = document.querySelector('.blind').clientWidth;
    height = document.querySelector('.blind').clientHeight;
    console.log(`width: ${width}`);
    console.log(`height: ${height}`);
  }) */

  let toggleSetting = (e) => {
    console.log(e.target.dataset.id);
    visible = !visible;
  };

  const handleResize = (e) => {
    width = document.querySelector('.blind').clientWidth;
    height = document.querySelector('.blind').clientHeight;
    console.log(width);
    console.log(height);
  }

</script>

<svelte:window on:resize={handleResize}/>

<div id="blinds">
  {#each blinds as blind (blind.id)}
    <div class="blind" data-id="{blind.id}" on:click={toggleSetting} style="width: {width}px; height: {height}px;">
      {#if blind.dim === 0}
        <img src="/img/blinds-0.svg" alt="Rollo {blind.room}" in:fade out:fade />
      {:else if blind.dim > 0 && blind.dim <= 25}
        <img src="/img/blinds-25.svg" alt="Rollo {blind.room}" in:fade out:fade />
      {:else if blind.dim > 25 && blind.dim <= 50}
        <img src="/img/blinds-50.svg" alt="Rollo {blind.room}" in:fade out:fade />
      {:else if blind.dim > 50 && blind.dim <= 75}
        <img src="/img/blinds-75.svg" alt="Rollo {blind.room}" in:fade out:fade />
      {:else}
        <img src="/img/blinds-100.svg" alt="Rollo {blind.room}" in:fade out:fade />
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
          Dim {blind.dim} <img
            class="icon"
            src="/img/percentage-solid.svg"
            width="9"
            alt="Percent"
          />
        </p>
        <p>
          {blind.power} Watt <img
            class="icon"
            src="/img/plug-solid.svg"
            width="9"
            alt="Plug"
          />
        </p>
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
    background-color: #4a4a4a;
    padding: 0.7rem;
    margin-bottom: 0.5rem;
    border-radius: 6px;
    cursor: pointer;
    position: relative;
  }
  .blind img {
    width: 80%;
    position: absolute;
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
</style>
