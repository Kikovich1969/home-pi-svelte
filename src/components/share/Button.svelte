<script>
  export let icon = false;
  export let label = "";
  export let backgroundColor = "white";
  export let color = "#363636";
  export let size = "medium";
  export let borderStyle = "solid";
  export let borderColor = "#dbdbdb";
  export let disabled = false;
  export let fullWidth = false;
  export let additionalStyles = "";

  let iconOnly = icon !== false && label === "" ? true : false;
</script>

<button
  class="button {size}"
  class:full-width={fullWidth}
  style="background-color: {backgroundColor}; color: {color}; border-style: {borderStyle}; border-color: {borderColor};{additionalStyles}"
  {disabled}
  on:click
>
  {#if icon}
    <span class="material-icons icons {size}" class:icon-only={iconOnly}>{icon}</span>
  {/if}
  {#if label !== ""}
    <span class="label">{label}</span>
  {/if}
</button>

<style>
  .button {
    display: inline-flex;
    border-width: 1px;
    cursor: pointer;
    align-items: center;
    justify-content: center;
    text-align: center;
    white-space: nowrap;
    padding: 0.6rem;
  }
  .icons,
  .label {
    display: inline-flex;
    align-items: center;
    justify-content: center;
  }
  .icons {
    margin-right: 0.3rem;
  }
  .label {
    padding-bottom: 2px;
  }
  .icon-only {
    margin-left: 0 !important;
    margin-right: 0 !important;
  }
  .large {
    border-radius: 0.7rem;
    font-size: 1.3rem;
    font-weight: 500;
    letter-spacing: 0.1rem;
  }
  .medium {
    border-radius: 0.5rem;
    font-size: 1rem;
    font-weight: 400;
  }
  .small {
    border-radius: 0.3rem;
    font-size: 0.75rem;
    font-weight: 400;
  }
  .button[disabled] {
    background-color: #fff;
    border-color: #dbdbdb;
    box-shadow: none;
    opacity: 0.5;
    cursor: not-allowed;
  }
  .full-width {
    width: 100%;
  }
</style>
