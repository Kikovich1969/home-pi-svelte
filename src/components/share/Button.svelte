<script>
  //import { createEventDispatcher } from "svelte";
  //const dispatch = createEventDispatcher();

  export const buttonText = "";
  export let buttonIcon = "";
  export let altTxt = "Button";

  /* const handleClick = () => {
    dispatch("doButtonClick");
  }; */
</script>

<div class="icon" on:click>
  <div>
    <img src={buttonIcon} alt="{altTxt}" />
  </div>
</div>

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
    cursor: pointer;
  }
  .icon img {
    width: 1rem;
  }
</style>
