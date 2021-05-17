<script>
  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";
  export let blinds;

  let noTransition = true;
  let hidden = [true, true, true];

  const hideAll = () => {
    hidden.forEach((v, i) => {
      hidden[i] = true;
    });
    hidden = [...hidden];
  };

  let toggleSetting = (id) => {
    hidden.forEach((v, i) => {
      if (i === id) {
        hidden[i] = !hidden[i];
      } else {
        hidden[i] = true;
      }
    });
    hidden = [...hidden];
  };
</script>

<div id="blinds">
  {#each blinds as blind (blind.id)}
    <button
      class="blind-link"
      on:click={() => {
        toggleSetting(blind.id);
      }}
    >
      <div class="blind" data-id={blind.id}>
        <img src="/img/frame.svg" class="frame" alt="Window" />
        {#if blind.dim === 0}
          <img
            src="/img/blinds-0.svg"
            class="blind-img"
            alt="Rollo {blind.room}"
            in:fade
            out:fade
            class:no-transition={noTransition}
          />
        {:else if blind.dim > 0 && blind.dim <= 30}
          <img
            src="/img/blinds-25.svg"
            class="blind-img"
            alt="Rollo {blind.room}"
            in:fade
            out:fade
            class:no-transition={noTransition}
          />
        {:else if blind.dim > 30 && blind.dim <= 60}
          <img
            src="/img/blinds-50.svg"
            class="blind-img"
            alt="Rollo {blind.room}"
            in:fade
            out:fade
            class:no-transition={noTransition}
          />
        {:else if blind.dim > 60 && blind.dim <= 99}
          <img
            src="/img/blinds-75.svg"
            class="blind-img"
            alt="Rollo {blind.room}"
            in:fade
            out:fade
            class:no-transition={noTransition}
          />
        {:else if blind.dim === 100}
          <img
            src="/img/blinds-100.svg"
            class="blind-img"
            alt="Rollo {blind.room}"
            in:fade
            out:fade
            class:no-transition={noTransition}
          />
        {/if}
      </div>
    </button>
  {/each}
</div>

{#each blinds as blind (blind.id)}
  {#if !hidden[blind.id]}
    <div class="blind-settings" data-id={blind.id} in:fade>
      {#if blind.id === 0}
        <span class="arrow-up arrow-is-left-top" />
      {:else if blind.id === 1}
        <span class="arrow-up arrow-is-center-top" />
      {:else if blind.id === 2}
        <span class="arrow-up arrow-is-right-top" />
      {/if}
      <h3>{blind.room}</h3>
      <div class="blind-controls">
        <p>
          Dim {blind.dim}%
        </p>
        <p>
          {blind.power} Watt
        </p>
        <section class="blind-buttons">
          <Button label="Open" />
          <Button label="Close" />
          <Button label="Set" />
        </section>
      </div>
      <div class="blind-slider">
        <input
          step="10"
          min="0"
          max="100"
          bind:value={blind.dim}
          type="range"
          on:focus={() => console.log('focus')}
        />
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
    width: 100%;
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
  .blind-settings {
    background-color: #fff;
    border-radius: 6px;
    color: #4a4a4a;
    padding: 0.3rem 1rem;
    position: relative;
  }
  .hidden {
    display: none;
  }
  .blind-settings h3 {
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

  .blind-link {
    background: none;
    border: none;
    box-shadow: none;
    padding: 0;
    width: 31%;
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
  .frame {
    width: 100%;
  }
  .no-transition {
    animation: none !important;
  }
  .arrow-up {
    width: 0;
    height: 0;
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-bottom: 8px solid white;
  }
  .arrow-is-left-top {
    position: absolute;
    top: -8px;
    left: 15%;
    transform: translateX(-4px);
  }
  .arrow-is-center-top {
    position: absolute;
    top: -8px;
    left: 50%;
    transform: translateX(-4px);
  }
  .arrow-is-right-top {
    position: absolute;
    top: -8px;
    left: 84%;
    transform: translateX(-4px);
  }
</style>
