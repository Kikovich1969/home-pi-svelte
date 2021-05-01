<script>
  import Button from "./share/Button.svelte";
</script>

<nav>
  <div class="brand">
    <img src="/img/woodstock_quad.svg" alt="Home Pi" />
  </div>
  <Button buttonIcon="/img/bars-solid.svg" />
</nav>

<style>
  .brand {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    background-color: transparent;
    border-radius: 0.2rem;
  }
  .brand:hover {
    background-color: #757d82;
    cursor: pointer;
  }
  .brand img {
    width: 1.5rem;
  }
  nav {
    background-color: #363636;
    color: #fff;
    min-height: 3.25rem;
    position: relative;
    display: flex;
    padding: 0.5rem;
    align-items: center;
    justify-content: space-between;
  }
</style>
