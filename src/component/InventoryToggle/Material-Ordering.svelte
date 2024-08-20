<script>
  import { INVENTORY } from "../../Javascript/MaterialStock";
</script>

<main>
  <div>
    <ul class="inventory-selector">
      <li><button>MATERIAL NAME</button></li>
      <li><button>UNIT</button></li>
      <li><button>MATERIAL DESCRIPTION</button></li>
      <li><button>UNIT PRICE</button></li>
      <li><button>ORDER QTY</button></li>
      <li><button>TOTAL AMOUNT</button></li>
      <li><button>DATE PURCHASE</button></li>
      <li><button>DELIVERY DATE</button></li>
      <li><button>ETA DATE</button></li>
      <li><button>ARRIVAL DATE</button></li>
      <li><button>STATUS </button></li>
      <li><button>VENDOR NAME</button></li>
      <li><button>VENDOR EMAIL</button></li>
      <li><button>VENDOR ADDRESS</button></li>
    </ul>
  </div>

  <div>
    {#each INVENTORY as inventory}
      <ul class="inventory-selector">
        <li class="inventory-item">{inventory.materialName}</li>
        <li class="inventory-item">{inventory.unit}</li>
        <li class="inventory-item">{inventory.materialdescription}</li>
        <li class="inventory-item">{inventory.unitprice}</li>
        <li class="inventory-item">{inventory.purchaseqty}</li>
        <li class="inventory-item">{inventory.totalPrice}</li>
        <li class="inventory-item">{inventory.datePurchase}</li>
        <li class="inventory-item">{inventory.deliverDate}</li>
        <li class="inventory-item">{inventory.etaDate}</li>
        <li class="inventory-item">{inventory.arrivalDate}</li>
        <li class="inventory-item">{inventory.status}</li>
        <li class="inventory-item">{inventory.vendor}</li>
        <li class="inventory-item">{inventory.vendorEmail}</li>
        <li class="inventory-item">{inventory.vendorAddress}</li>
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
    width: 8.1rem;
    height: 3rem;
    font-size: 12px;
    font-weight: 600;
    border: none;
  }

  .inventory-item {
    display: block;
    width: 8.1rem;
    height: 4rem;
    font-size: 12px;
    font-weight: 600;
    align-content: center;
    border: none;
    letter-spacing: 1px;
    font-family: sans-serif;
  }
</style>
