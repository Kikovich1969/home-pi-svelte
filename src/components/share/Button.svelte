<script>
  export let buttonText = "";
  export let buttonIcon = "";
  export let altTxt = "Button";
</script>

<div class="button" on:click>
  <div>
    {#if buttonIcon !== ""}
      <img src={buttonIcon} alt={altTxt} />
    {/if}
    {buttonText}
  </div>
</div>

<style>
  .button {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    background-color: transparent;
    border-radius: 0.2rem;
    border: 1px solid #4a4a4a;
  }
  .button:hover {
    background-color: #757d82;
    cursor: pointer;
  }
  .button img {
    width: 1rem;
  }
</style>
