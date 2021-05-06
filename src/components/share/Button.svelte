<script>
  /* Defaults */
  export let backgroundColor = "white";
  export let borderColor = "black";
  export let color = "black";
  export let size = "medium";
</script>

<div class="buttons" on:click>
  <div
    class="button {size}"
    style="background-color: {backgroundColor}; border-color: {borderColor}; color: {color};"
  >
    <slot />
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
    border-width: 1px;
    border-style: solid;
    cursor: pointer;
    justify-content: center;
    text-align: center;
    white-space: nowrap;
    padding-bottom: calc(0.5em - 1px);
    padding-top: calc(0.5em - 4px);
    padding-left: 0.6rem;
    padding-right: 0.6rem;
    border-radius: 0.5rem;
  }
  .large {
    font-size: 1.3rem;
    font-weight: 500;
  }
  .medium {
    font-size: 1rem;
    font-weight: 400;
  }
  .small {
    font-size: 0.75rem;
    font-weight: 400;
  }
</style>
