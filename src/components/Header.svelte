<script>
  import Button from "./share/Button.svelte";
  import { fade } from "svelte/transition";
  let visible = false;
  const toggleMenu = () => {
    visible = !visible;
  };
</script>

<nav>
  <div class="nav-bar">
    <div class="nav-brand">
      <img src="/img/woodstock_quad.svg" alt="Home Pi" />
    </div>
    <Button buttonIcon="/img/bars-solid.svg" altTxt="Burger Menu" on:click={toggleMenu} />
  </div>
  {#if visible}
    <div class="nav-menu" transition:fade={{ duration: 100 }}>
      <a href="#">Dashboard</a>
      <a href="#">Settings</a>
    </div>
  {/if}
</nav>

<style>
  nav {
    background-color: #363636;
    color: #fff;
    min-height: 3.25rem;
    position: relative;
  }
  .nav-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.5rem;
    background-color: transparent;
  }
  .nav-brand {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0.5rem;
    border-radius: 0.2rem;
  }
  .nav-brand:hover {
    cursor: pointer;
  }
  .nav-brand img {
    width: 1.75rem;
  }
  .nav-menu {
    background-color: white;
    text-align: right;
  }
  .nav-menu a {
    display: block;
    color: #4a4a4a;
    text-decoration: none;
    padding: 0.5rem 0.75rem;
  }
</style>
