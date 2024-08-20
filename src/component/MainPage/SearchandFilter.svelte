<script>
    import { onMount } from "svelte";
  
    import { PRODUCTS } from "../Store";
    import SearchInput from "./SearchInput.svelte";
    import Menu from "./Menu.svelte";
    import NoResult from "./NoResult.svelte";
    import ProductSearch from "./Product-search.svelte";
  
    let languages = [];
    let selectedLang = "";
    let searchProduct = "";
    let filteredProducts = [];
  
    const getLanguages = () => {
      languages = [...new Set(PRODUCTS.map(product => product.productName))].sort();
    };
  
    onMount(() => {
      getLanguages();
      filterProducts(); // Ensure filtering happens on mount
    });
  
    $: filterProducts = () => {
      filteredProducts = PRODUCTS.filter(product => {
        const matchesLang = selectedLang === "" || selectedLang === "all" || product.productName === selectedLang;
        const matchesSearch = !searchProduct || product.productName.toLowerCase().includes(searchProduct.toLowerCase());
        return matchesLang && matchesSearch;
      });
    };
  
    $: filterProducts();
  </script>
  
  <section id="query-section">
    <Menu {languages} bind:selectedLang />
    <SearchInput bind:searchProduct />
  </section>
  
  <main id="bookshelf">
    {#if searchProduct && filteredProducts.length === 0}
      <NoResult />
    {:else if filteredProducts.length > 0}
      {#each filteredProducts as { img, productName, unitOfMeasurement, description, brand }}
        <ProductSearch
          {img}
          {productName}
          {unitOfMeasurement}
          {description}
          {brand}
        />
      {/each}
    {:else}
      {#each PRODUCTS as { img, productName, unitOfMeasurement, description, brand }}
        <ProductSearch
          {img}
          {productName}
          {unitOfMeasurement}
          {description}
          {brand}
        />
      {/each}
    {/if}
  </main>
  
  <style>
    * {
      box-sizing: border-box;
    }
  
    #query-section {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 2% 0;
    }
  
    main#bookshelf {
      width: 100%;
      margin: 10px;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      align-items: flex-start;
      justify-content: center;
    }
  </style>
  