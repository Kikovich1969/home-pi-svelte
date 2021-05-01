<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let buttonText = "";
  export let buttonIcon = "";

  const handleClick = () => {
    dispatch("doButtonClick");
  };
</script>

<div class="icon">
  <div>
    <img src={buttonIcon} alt="Burger Menu" />
  </div>
</div>

<!-- <button on:click={handleClick} class:promo={isPromo}>{buttonText}</button> -->
<style>
  .icon {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    background-color: transparent;
    border-radius: 0.2rem;
  }
  .icon:hover {
    background-color: #757d82;
  }
  .icon img {
    width: 1rem;
  }
</style>
