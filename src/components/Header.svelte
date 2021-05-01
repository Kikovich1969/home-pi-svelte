<script>
  import Button from "./share/Button.svelte";
</script>

<nav>
  <div class="icon brand">
    <div>
      <img src="/img/woodstock_quad.svg" alt="Home Pi" />
    </div>
  </div>
  <Button buttonIcon="/img/bars-solid.svg" />
  <!-- <div class="icon burger">
    <div>
      <img src="/img/bars-solid.svg" alt="Burger Menu" />
    </div>
  </div> -->
</nav>

<style>
  .icon {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    background-color: transparent;
    /*border: 1px solid white;*/
    border-radius: 0.2rem;
  }
  .icon:hover {
    background-color: #827575;
    cursor: pointer;
  }
  .brand img,
  .burger img {
    width: 1rem;
  }
  nav {
    background-color: #363636;
    color: #fff;
    min-height: 3.25rem;
    position: relative;
    display: flex;
    padding: 1rem;
    align-items: center;
    justify-content: space-between;
  }
</style>
