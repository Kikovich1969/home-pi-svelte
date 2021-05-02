<script>
  import Button from "./share/Button.svelte";
  let hideMenu = true;
  const toggleMenu = () => {
    hideMenu = !hideMenu;
  };
</script>

<nav>
  <div class="nav-bar">
    <div class="nav-brand">
      <img src="/img/woodstock_quad.svg" alt="Home Pi" />
    </div>
    <Button buttonIcon="/img/bars-solid.svg" on:click={toggleMenu} />
  </div>

  <div class="nav-menu" class:hide={hideMenu}>
    <a href="#">Dashboard</a>
    <a href="#">Settings</a>
  </div>
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
    width: 1.5rem;
  }
  .nav-menu {
    background-color: white;
    text-align: right;
  }
  .hide {
    display: none;
  }
  .nav-menu a {
    display: block;
    color: #4a4a4a;
    text-decoration: none;
    padding: 0.5rem 0.75rem;
  }
</style>
