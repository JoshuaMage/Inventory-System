<script>
  import { Router, Route, navigate, Link } from "svelte-routing";

  import Products from "./Products.svelte";
  import Inventory from "./Inventory.svelte";
  import Sales from "./Sales.svelte";

  import logo from "../../image/Hardwarelogo.png";

  import Kilogram from "../ProductToggle/Kilogram.svelte";
  import Pc from "../ProductToggle/Pc.svelte";
  import Liter from "../ProductToggle/Liter.svelte";
  import Meter from "../ProductToggle/Meter.svelte";

  let showToggleProduct = false;
  let showToggleInventory = false;
  let showToggleSales = false;

  function goToProduct() {
    showToggleProduct = !showToggleProduct;
    showToggleInventory = false;
    showToggleSales = false;
    navigate("/products");
  }

  function goToInventory() {
    showToggleInventory = !showToggleInventory;
    showToggleProduct = false;
    showToggleSales = false;
    navigate("/inventory");
  }

  function goToSales() {
    showToggleSales = !showToggleSales;
    showToggleProduct = false;
    showToggleInventory = false;
    navigate("/sales");
  }
</script>

<Router>
  <main>
    <div class="page-selector">
      <section class="buttonSelector">
        <img src={logo} alt="company logo" class="magelogo" />
        <div class="button-section">
          <button on:click={goToProduct} class="button-pages">PRODUCT</button>
          <nav class:open={showToggleProduct}>
            <ul>
              <li><Link to="productKg" class="link">Kg</Link></li>
              <li><Link to="productPc" class="link">Pc</Link></li>
              <li><Link to="productLiter" class="link">Liters</Link></li>
              <li><Link to="productMeter" class="link">Meter</Link></li>
            </ul>
          </nav>
        </div>

        <div class="button-section">
          <button on:click={goToInventory} class="button-pages">INVENTORY</button>
          <nav class:open={showToggleInventory}>
            <ul>
              <li><Link to="" class="link">Material Stock</Link></li>
              <li><Link to="" class="link">Material List</Link></li>
              <li><Link to="" class="link">Material Purchase</Link></li>
              <li><Link to="" class="link">Supplier Details</Link></li>
              <li><Link to="" class="link">Material Ordering</Link></li>
            </ul>
          </nav>
        </div>

        <div class="button-section">
          <button on:click={goToSales} class="button-pages">SALE</button>
          <nav class:open={showToggleSales}>
            <ul>
              <li><Link to="" class="link">Summary Sales</Link></li>
              <li><Link to="" class="link">Income Statement</Link></li>
            </ul>
          </nav>
        </div>
        <input
          type="text"
          placeholder="Search Product..."
          class="search-pages"
        />
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

  <Route path="/products" component={Products} />
  <Route path="/inventory" component={Inventory} />
  <Route path="/sales" component={Sales} />
  <Route path="/productKg" component={Kilogram} />
  <Route path="/productPc" component={Pc} />
  <Route path="/productLiter" component={Liter} />
  <Route path="/productMeter" component={Meter} />
</Router>

<style>
  .button-section {
    position: relative;
    padding: 0 10px;
  }

  nav {
    display: none;
  }

  nav.open {
    display: block;
    position: absolute;
    left: 20px;
  }

  ul {
    background-color: transparent;
    border: 1.2px solid black;
    border-radius: 5px;
  }

  ul li {
    list-style-type: none;
    width: 9rem;
    border: 1px solid black;
  }

  :global(nav ul li a.link) {
    color: black;
    letter-spacing: 1px;
    text-decoration: none;
  }

  :global(nav ul li a.link:hover) {
    color: white;
    background-color: black;
    padding: 0 7px;
  }

  .page-selector {
    display: grid;
    grid-template-columns: 1fr 0.2fr;
    background-color: #f5f7f8;
    padding: 4rem;
    background-image: url("https://wallpaperaccess.com/full/4255421.jpg");
    background-size: cover;
  }

  .buttonSelector {
    display: flex;
    text-align: center;
    align-items: center;
  }

  .magelogo {
    transform: translateX(-50px);
    height: 10rem;
    width: 10rem;
    border-radius: 50%;
  }

  .button-pages {
    width: 10rem;
    border-radius: 1rem;
    font-size: 1.2rem;
    font-weight: 800;
    background-color: transparent;
    border: transparent;
  }

  .button-pages:active {
    color: #f24c3d;
  }

  .buttonSelector input {
    transform: translateX(5rem);
    height: 2.5rem;
    width: 80%;
    max-width: 25rem;
    border-radius: 1rem;
    font-size: 1rem;
    font-weight: 600;
    text-align: center;
  }

  .user {
    transform: translateX(80px);
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
