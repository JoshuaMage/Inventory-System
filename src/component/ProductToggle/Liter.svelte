<script>
    import { PRODUCTS } from "../Store";
    import Footer from "../MainPage/Footer.svelte";
  
    function handleIntersection(entries) {
      entries.forEach((entry) => {
        entry.target.style.opacity = entry.isIntersecting ? "1" : "0";
        entry.target.style.transition = "opacity 1.5s ease-in-out";
      });
    }
  
    function observeIntersection(node) {
      const observer = new IntersectionObserver(handleIntersection, {
        threshold: [0.1, 0.5, 1.0], // Adjust thresholds as needed
      });
      observer.observe(node);
  
      return {
        destroy() {
          observer.unobserve(node);
        },
      };
    }

    $: LiterProducts = $PRODUCTS.filter(product => product.unitOfMeasurement === "liters")
  </script>
  
  <main>
    <div class="product-list">
      {#each LiterProducts as PRODUCT}
        <section class="product-detail" use:observeIntersection>
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
  <Footer />
  
  <style>
@import "../../css/product.css";
  </style>
  