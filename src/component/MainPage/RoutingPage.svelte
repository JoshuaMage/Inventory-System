<script>
  import { Router, Route, navigate } from "svelte-routing";

  import Products from "./Products.svelte";
  import Inventory from "./Inventory.svelte";
  import Sales from "./Sales.svelte";

  import logo from "../../image/Hardwarelogo.png";

  function goToProduct() {
    console.log("product click");
    navigate("/products");
  }

  function goToInventory() {
    console.log("inventort click");
    navigate("/inventory");
  }

  function goToSales() {
    console.log("sales click");
    navigate("/sales");
  }
</script>

<main>
  <div class="page-selector">
    <section class="buttonSelector">
      <img src={logo} alt="componay logo" class="magelogo" />
      <button on:click={goToProduct} class="button-pages">PRODUCT</button>
      <button on:click={goToInventory} class="button-pages">PURCHASE</button>
      <button on:click={goToSales} class="button-pages">SALE</button>
      <input type="text" placeholder="Search Product..." class="search-pages" />
    </section>
    <section class="user">
      <h4>
        <svg
          width="50px"
          height="50px"
          viewBox="0 0 1 1"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          ><path
            width="16"
            height="16"
            id="icon-bound"
            fill="none"
            d="M0 0H1V1H0V0z"
          /><path
            d="M0.5 0.5a0.25 0.25 0 1 0 0 -0.5 0.25 0.25 0 0 0 0 0.5m0.25 0.125H0.25a0.25 0.25 0 0 0 -0.25 0.25v0.125h1v-0.125a0.25 0.25 0 0 0 -0.25 -0.25"
          /></svg
        >
      </h4>
      <section>
        <h3>User</h3>
        <select name="" id="">
          <option value="">Log-out</option>
          <option value="">Setting</option>
        </select>
      </section>
    </section>
  </div>
</main>

<Router>
  <Route path="/products" component={Products} />
  <Route path="/inventory" component={Inventory} />
  <Route path="/sales" component={Sales} />
</Router>

<style>
  .page-selector {
    display: grid;
    grid-template-columns: 1fr 0.2fr;
    background-color: #f5f7f8;
    padding: 2rem;
    background-image: url("https://wallpaperaccess.com/full/4255421.jpg");
    background-size: cover;
  }

  .buttonSelector {
    display: flex;
    text-align: center;
    align-items: center;
  }

  .magelogo {
    height: 10rem;
    width: 10rem;
    border-radius: 50%;
  }

  .button-pages {
    width: 11rem;
    border-radius: 1rem;
    font-size: 1.2rem;
    font-weight: 800;
    background-color: transparent;
    border: transparent;
  }

  .button-pages:active {
    color: red;
  }

  .buttonSelector input {
    transform: translateX(30rem);
    height: 2.5rem;
    width: 25rem;
    border-radius: 1rem;
    font-size: 1rem;
    font-weight: 600;
    text-align: center;
  }

.user {
    transform: translateX(50px);
}

.user h3 {
  color: black;
  font-weight: 700;
}

.user select {
  height: 2rem;
  width: 10rem;
  text-align: center;
  border-radius: 10px;
}
</style>
