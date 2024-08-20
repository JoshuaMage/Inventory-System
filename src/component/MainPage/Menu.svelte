<script>
    export let languages = [];
    export let selectedLang = "";
  </script>
  
  <section class="menu-cont">
    <select class="menu" bind:value={selectedLang}>
      <option value="all">All Products</option>
      {#each languages as language}
        <option value={language}>{language}</option>
      {/each}
    </select>
  </section>
  
  <style>
    .menu-cont {
      width: 40%;
      display: flex;
      margin: 0 10px 0 0;
    }
  
    select {
      margin: 0;
      font-size: 1.18rem;
      border: 1px solid gray;
      border-radius: 5px;
    }
  
    .menu {
      width: 100%;
    }
  </style>
  