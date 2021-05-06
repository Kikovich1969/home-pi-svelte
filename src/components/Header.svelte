<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  import Button from "./share/Button.svelte";
  import Clock from "./share/Clock.svelte";
  import { fade } from "svelte/transition";

  let burger = {
    icon: "menu",
    backgroundColor: "transparent",
    borderColor: "#363636",
    color: "white",
    size: "medium",
    label: "",
  };

  let visible = false;

  const setCurrentPage = (e) => {
    dispatch("setCurrentPage", e);
    visible = false;
  };
  const toggleMenu = () => {
    visible = !visible;
  };
</script>

<nav>
  <div class="nav-bar">
    <div class="nav-brand">
      <a on:click={setCurrentPage}>
        <img src="/img/woodstock_quad.svg" alt="Home Pi" data-target="Dashboard" />
      </a>
    </div>
    <Clock />
    <div class="burger-menu-wrapper">
      <Button {...burger} on:click={toggleMenu} />
    </div>
    <div class="nav-menu-horizontal">
      <a on:click={setCurrentPage} data-target="Dashboard">Dashboard</a>
      <a on:click={setCurrentPage} data-target="Settings">Settings</a>
      <a on:click={setCurrentPage} data-target="History">History</a>
    </div>
  </div>
  {#if visible}
    <div class="nav-menu" transition:fade={{ duration: 100 }}>
      <a on:click={setCurrentPage} data-target="Dashboard">Dashboard</a>
      <a on:click={setCurrentPage} data-target="Settings">Settings</a>
      <a on:click={setCurrentPage} data-target="History">History</a>
    </div>
  {/if}
</nav>

<style>
  @media screen and (min-width: 769px) {
    .burger-menu-wrapper,
    .nav-menu {
      display: none;
    }
    .nav-menu-horizontal {
      display: block !important;
    }
  }
  nav {
    background-color: #363636;
    color: #fff;
    min-height: 3.25rem;
    position: relative;
  }
  .nav-menu-horizontal {
    display: none;
  }
  .nav-menu-horizontal a {
    color: white;
    display: inline-block;
    padding: 0.5rem;
    text-decoration: none;
    cursor: pointer;
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
    cursor: pointer;
  }
  .burger-menu-wrapper {
    display: flex;
    align-items: center;
  }
</style>
