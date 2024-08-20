<script>
  import "../src/app.css";
  import Footer from "./component/MainPage/Footer.svelte";
  import RoutingPage from "./component/MainPage/RoutingPage.svelte";
</script>

<main>
  <div class="wrapper">
    <RoutingPage />
  </div>
  <Footer />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .wrapper {
    flex: 1;
  }
  
</style>
