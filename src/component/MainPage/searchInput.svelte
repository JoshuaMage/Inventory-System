<script>
  export let searchProduct = "";
</script>

<div>
  <input
    type="text"
    placeholder="Search Product..."
    autocomplete="off"
    bind:value={searchProduct}
  />
</div>

<style>
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
</style>
