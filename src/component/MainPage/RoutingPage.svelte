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

  import MaterialList from "../InventoryToggle/Material-List.svelte";
  import MaterialOrdering from "../InventoryToggle/Material-Ordering.svelte";
  import MaterialPurchase from "../InventoryToggle/Material-Purchase.svelte";
  import StockInOut from "../InventoryToggle/Stockin-Stockout.svelte";
  import SupplierInformation from "../InventoryToggle/Supplier-Information.svelte";
  import WarehouseStock from "../InventoryToggle/Warehouse-Stock.svelte";



  let showToggleProduct = false;
  let showToggleInventory = false;
  let showToggleSales = false;
  let searchProduct = "";

  function goToProduct() {
    showToggleProduct = !showToggleProduct;
    showToggleInventory = false;
    showToggleSales = false;
    navigate("/products");
  }

  function handleProductClick() {
    showToggleProduct = false;
    navigate("/products");
  }

  function goToInventory() {
    showToggleInventory = !showToggleInventory;
    showToggleProduct = false;
    showToggleSales = false;
    navigate("/inventory");
  }

  function handleInventoryClick() {
    showToggleInventory = false;
    navigate("inventory");
  }

  function goToSales() {
    showToggleSales = !showToggleSales;
    showToggleProduct = false;
    showToggleInventory = false;
    navigate("/sales");
  }

  function handleSalesClick() {
    showToggleSales = false;
    navigate("/sales");
  }

  
  
</script>



<Router>
  <main>
    <div class="page-selector">
      <section class="buttonSelector">
        <img src={logo} alt="company logo" class="magelogo" />

        <!-- Product Section -->
        <div class="button-section">
          <button on:click={goToProduct} class="button-pages">PRODUCT</button>
          <nav class:open={showToggleProduct}>
            <ul>
              <li>
                <Link
                  to="productKg"
                  on:click={() => handleProductClick()}
                  class="link">Kg</Link
                >
              </li>
              <li>
                <Link
                  to="productPc"
                  on:click={() => handleProductClick()}
                  class="link">Pc</Link
                >
              </li>
              <li>
                <Link
                  to="productLiter"
                  on:click={() => handleProductClick()}
                  class="link">Liters</Link
                >
              </li>
              <li>
                <Link
                  to="productMeter"
                  on:click={() => handleProductClick()}
                  class="link">Meter</Link
                >
              </li>
            </ul>
          </nav>
        </div>

        <!-- Inventory Section -->
        <div class="button-section">
          <button on:click={goToInventory} class="button-pages"
            >INVENTORY</button
          >
          <nav class:open={showToggleInventory}>
            <ul class="inventory-selector">
              <li>
                <Link
                  to="materialstock-InOut"
                  on:click={() => handleInventoryClick()}
                  class="link">Material STOCK IN/OUT</Link
                >
              </li>
              <li>
                <Link
                  to="warehouse-stock"
                  on:click={() => handleInventoryClick()}
                  class="link">Warehouse Stock</Link
                >
              </li>
              <li>
                <Link
                  to="material-list"
                  on:click={() => handleInventoryClick()}
                  class="link">Material List</Link
                >
              </li>
              <li>
                <Link
                  to="material-purchase"
                  on:click={() => handleInventoryClick()}
                  class="link">Material Purchase</Link
                >
              </li>
              <li>
                <Link
                  to="supplier-information"
                  on:click={() => handleInventoryClick()}
                  class="link">Supplier Details</Link
                >
              </li>
              <li>
                <Link
                  to="material-ordering"
                  on:click={() => handleInventoryClick()}
                  class="link">Material Ordering</Link
                >
              </li>
            </ul>
          </nav>
        </div>

        <!-- Sales Section -->
        <div class="button-section">
          <button on:click={goToSales} class="button-pages">SALE</button>
          <nav class:open={showToggleSales}>
            <ul>
              <li>
                <Link to="" on:click={() => handleSalesClick()} class="link"
                  >Summary Sales</Link
                >
              </li>
              <li>
                <Link to="" on:click={() => handleSalesClick()} class="link"
                  >Income Statement</Link
                >
              </li>
            </ul>
          </nav>
        </div>

        <!-- Search Input -->
    <input type="text">
      </section>

      <!-- User Section -->
      <section class="user">
        <section>
          <h4>
            <svg
              width="50px"
              height="50px"
              viewBox="0 0 1 1"
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                width="16"
                height="16"
                id="icon-bound"
                fill="none"
                d="M0 0H1V1H0V0z"
              />
              <path
                d="M0.5 0.5a0.25 0.25 0 1 0 0 -0.5 0.25 0.25 0 0 0 0 0.5m0.25 0.125H0.25a0.25 0.25 0 0 0 -0.25 0.25v0.125h1v-0.125a0.25 0.25 0 0 0 -0.25 -0.25"
              />
            </svg>
          </h4>
          <h3>User</h3>
        </section>
        <section>
          <select>
            <option value="">Log-out</option>
            <option value="">Setting</option>
          </select>
        </section>
      </section>
    </div>
  
  </main>

  <!-- Routes -->
  <Route path="/products" component={Products} />
  <Route path="/inventory" component={Inventory} />
  <Route path="/sales" component={Sales} />

  <Route path="/productKg" component={Kilogram} />
  <Route path="/productPc" component={Pc} />
  <Route path="/productLiter" component={Liter} />
  <Route path="/productMeter" component={Meter} />

  <Route path="/material-list" component={MaterialList} />
  <Route path="/material-ordering" component={MaterialOrdering} />
  <Route path="/material-purchase" component={MaterialPurchase} />
  <Route path="/materialstock-InOut" component={StockInOut} />
  <Route path="/supplier-information" component={SupplierInformation} />
  <Route path="/warehouse-stock" component={WarehouseStock} />
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
    border: 1.2px solid black;
    border-radius: 5px;
  }

  ul li {
    background-color: transparent;
    list-style-type: none;
    width: 9rem;
    border: 1px solid black;
  }

  ul li:hover {
    background-color: black;
    color: white;
  }

  input {
    transform: translateX(5rem);
    height: 2.5rem;
    width: 30rem;
    max-width: 25rem;
    border-radius: 5px;
    font-size: 1rem;
    font-weight: 600;
    text-align: center;
  }

  input:hover {
    height: 3rem;
  }

  :global(nav ul li a.link) {
    color: black;
    letter-spacing: 1px;
    text-decoration: none;
  }

  :global(nav ul li a.link:hover) {
    color: white;
  }

  .page-selector {
    display: grid;
    grid-template-columns: 1fr 0.2fr;
    background-color: #eeeded;
    padding-top: 1rem;
    padding-bottom: 6rem;
    padding-left: 2rem;
    padding-right: 2rem;
  }

  .buttonSelector {
    display: flex;
    text-align: center;
    align-items: center;
  }

  .magelogo {
    height: 13rem;
    width: 13rem;
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

  .user {
    display: flex;
    flex-direction: column;
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
