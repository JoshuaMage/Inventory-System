<script>
// @ts-nocheck

  import { PRODUCTS } from "../Store";
</script>

<main>
  <div class="product-list">
    {#each $PRODUCTS as PRODUCT}
      <section class="product-detail">
        <img src={PRODUCT.img} alt={PRODUCT.productName} />
        <section>
        <h1>{PRODUCT.productName}</h1>
        <h2>({PRODUCT.unitOfMeasurement})</h2>
        <p>{PRODUCT.description}</p>
        <h4>{PRODUCT.brand}</h4>
    </section>
      </section>
    {/each}
  </div>
</main>

<style>
  main {
    display: grid;
    justify-content: center;
    width: 100%;
  }

  .product-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
    gap: 1rem;
  }

  .product-detail {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: repeat(2, 1fr);
    background-color: #f5f5f5;
    place-items: center;
    padding: 10px;
  }

  img {
    max-width: 100%;
    height: 10rem;
    justify-content: center;
    object-fit: cover;
    padding: 1rem;
  }

  h1 {
    font-size: 2rem;
    font-weight: 800;
    letter-spacing: 2px;
  }
  h2 {
    font-size: 1.3rem;
    font-weight: 500;
    color: #686d76;
  }
  p {
    letter-spacing: 1.5px;
  }
  h4 {
    font-size: 1.5rem;
    letter-spacing: 2px;
    color: #ffb200;
  }
</style>
