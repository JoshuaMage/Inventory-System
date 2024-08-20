<script>
  import { INVENTORY } from "../../Javascript/MaterialStock";

</script>

<main>
  <div>
    <ul class="inventory-selector">
      <li><button>DATE</button></li>
      <li><button>MATERIAL CODE</button></li>
      <li><button>MATERIAL NAME</button></li>
      <li><button>MATERIAL DESCRIPTION</button></li>
      <li><button>UNIT</button></li>
      <li><button>STOCK-IN</button></li>
      <li><button>STOCK-OUT</button></li>
      <li><button>PURCHASE QTY</button></li>
      <li><button>REMARKS</button></li>
    </ul>
  </div>

  <div>
    {#each INVENTORY as inventory}
      <ul class="inventory-selector">
        <li class="inventory-item">{inventory.date}</li>
        <li class="inventory-item">{inventory.materialCode}</li>
        <li class="inventory-item">{inventory.materialName}</li>
        <li class="inventory-item">{inventory.materialdescription}</li>
        <li class="inventory-item">{inventory.unit}</li>
        <li class="inventory-item">{inventory.stockin}</li>
        <li class="inventory-item">{inventory.stockout}</li>
        <li class="inventory-item">{inventory.purchaseqty}</li>
        <li class="inventory-item">{inventory.status}</li>
      </ul>
    {/each}
  </div>
</main>

<style>
main {
  margin: 2rem;
}

  .inventory-selector {
    display: flex;
    flex-wrap: nowrap;
    justify-content: center;
  }

  .inventory-selector li {
    list-style-type: none;
    border: 1px solid black;
  }

  .inventory-selector button {
    width: 10rem;
    height: 3rem;
    font-size: 12px;
    font-weight: 600;
    border: none;
  }

  .inventory-item {
    display: block;
    width: 10rem;
    height: 4rem;
    font-size: 12px;
    font-weight: 600;
    align-content: center;
    border: none;
    letter-spacing: 1px;
    font-family: sans-serif;
  }

</style>
