<script>
  import ComLogo from "../image/Hardwarelogo.png";
  import Login from "./Login.svelte";
  import CreateAccount from "./CreateAccount.svelte";

  let showForm = true;
  let showLogin = false;
  let showCreateAccount = false;

  function showLoginForm() {
    showForm = false;
    showLogin = true;
    showCreateAccount = false;
  }

  function showCreateAccountForm() {
    showForm = false;
    showLogin = false;
    showCreateAccount = true;
  }
</script>

{#if showForm}
  <main>
    <div class="signUpForm">
      <img src={ComLogo} alt="Hardware Logo" />
      <section>
        <button on:click={showLoginForm}>Log-in</button>
        <button on:click={showCreateAccountForm}>Create Account</button>
      </section>
    </div>
  </main>
{:else if showLogin}
  <Login />
{:else if showCreateAccount}
  <CreateAccount />
{/if}

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    padding: 20px;
  }

  .signUpForm {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    background-image: url("https://wallpaperaccess.com/full/4255421.jpg");
    background-size: cover;
    width: 100%;
    max-width: 70rem;
    height: 40rem;
    padding: 20px;
    border-radius: 10px;
  }

  .signUpForm img {
    height: 100%;
    justify-content: center;
    align-self: center;
    border-radius: 10px;
  }

  .signUpForm section {
    display: flex;
    flex-direction: column;
    text-align: center;
    justify-content: center;
  }

  .signUpForm section button {
    width: 25rem;
    height: 4rem;
    border-radius: 5px;
    text-align: center;
    align-self: center;
    margin: 10px;
    font-size: 1.2rem;
    font-weight: 700;
  }

  .signUpForm section button:active {
    background-color: red;
    color: white;
  }
</style>
