<script>
  import { INVENTORY } from "../../Javascript/MaterialStock";
</script>

<main>
  <div>
    <ul class="inventory-selector">
      <li><button>VENDOR NAME</button></li>
      <li><button>VENDOR PHONE#</button></li>
      <li><button>VENDOR TELEPHONE#</button></li>
      <li><button>VENDOR EMAIL</button></li>
      <li><button>VENDOR ADDRESS</button></li>
      <li><button>BANK ACCOUNT</button></li>
      <li><button>REMARKS</button></li>
    </ul>
  </div>

  <div>
    {#each INVENTORY as inventory}
      <ul class="inventory-selector">
        <li class="inventory-item">{inventory.vendor}</li>
        <li class="inventory-item">{inventory.vendorPhonenumber}</li>
        <li class="inventory-item">{inventory.vendorTelephone}</li>
        <li class="inventory-item">{inventory.vendorEmail}</li>
        <li class="inventory-item">{inventory.vendorAddress}</li>
        <li class="inventory-item">{inventory.vendeorBankAcc}</li>
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
    width: 8.5rem;
    height: 3rem;
    font-size: 12px;
    font-weight: 600;
    border: none;
  }

  .inventory-item {
    display: block;
    width: 8.5rem;
    height: 4rem;
    font-size: 12px;
    font-weight: 600;
    align-content: center;
    border: none;
    letter-spacing: 1px;
    font-family: sans-serif;
  }
</style>
