<script>
  import Icon from "./Run.svelte";

  export let icon = false;
  export let svg = null;
  export let backgroundColor = "white";
  export let color = "black";
  export let size = "medium";
</script>

<div class="buttons">
  <div
      class="button {size}"
      style="background-color: {backgroundColor}; color: {color};"
  >
      {#if icon}
          <Icon />
      {/if}
      <slot>Click me!</slot>
  </div>
</div>

<style>
  .buttons {
      align-items: center;
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-start;
  }
  .button {
      background-color: #fff;
      border-color: black;
      border-width: 1px;
      color: #363636;
      cursor: pointer;
      justify-content: center;
      text-align: center;
      white-space: nowrap;
  }
  .large {
      border-radius: 0.7rem;
      padding-bottom: calc(0.5em - 1px);
      padding-top: calc(0.5em - 4px);
      padding-left: 1rem;
      padding-right: 1rem;
      font-size: 1.3rem;
      font-weight: 500;
      letter-spacing: 0.1rem;
  }
  .medium {
      border-radius: 0.5rem;
      padding-bottom: calc(0.5em - 1px);
      padding-top: calc(0.5em - 4px);
      padding-left: 0.6rem;
      padding-right: 0.6rem;
      font-size: 1rem;
      font-weight: 400;
  }
  .small {
      border-radius: 0.3rem;
      padding-bottom: calc(0.5em - 1px);
      padding-top: calc(0.5em - 3px);
      padding-left: 0.4rem;
      padding-right: 0.4rem;
      font-size: 0.75rem;
      font-weight: 400;
      letter-spacing: 0.05rem;
  }
</style>
