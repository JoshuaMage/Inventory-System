<script>
  import ComLogo from "../image/Hardwarelogo.png";
  import Loginform from "./Loginform.svelte";
  import MainLayout from "./MainLayout.svelte";

  let showLogin = true;
  let showForm = false;
  let isLoading = false;

  let employeeId = "";
  let password = "";
  let employeeIdError = false;
  let passwordError = false;

  function showLoginForm() {
    isLoading = true;
    setTimeout(() => {
      showLogin = false;
      showForm = true;
      isLoading = false;
    }, 1000); // Adjust the timeout duration as needed
  }

  function showWebsite() {
    isLoading = true;
    setTimeout(() => {
      showLogin = false;
      showForm = true;
      isLoading = false;
    }, 1000); // Adjust the timeout duration as needed
  }

  function handleSubmit(event) {
    event.preventDefault();

    employeeIdError = !employeeId;
    passwordError = !password;
  }
</script>

<main>
  {#if showLogin}
    <div class="signUpForm">
      <img src={ComLogo} alt="Hardware Logo" />

      <section>
        <form on:submit={handleSubmit} class="form">
          <section>
            <label for="employeeId">Employee-ID</label>
            <input
              type="number"
              class="signin-input"
              id="employeeId"
              bind:value={employeeId}
              class:error={employeeIdError}
              required
            />
          </section>
          <section>
            <label for="">Password</label>
            <input
              type="password"
              class="signin-input"
              id="password"
              bind:value={password}
              class:error={passwordError}
              required
            />
          </section>
          <section class="button-login">
            <button type="submit" on:click={showWebsite}>Sign-in</button>
            <button type="button" on:click={showLoginForm}
              >Forgot password</button
            >
          </section>
        </form>
      </section>
    </div>
  {:else}
    <Loginform />
  {/if}
</main>

<style>
  @import "../css/Signup.css";

  .signUpForm {
    background-image: url("https://wallpaperaccess.com/full/4255421.jpg");
    background-size: cover;
  }

  form {
    margin-bottom: 5rem;
  }

  form section {
    margin-bottom: 2rem;
  }

  label {
    color: black;
    font-weight: 800;
  }
  .signin-input {
    height: 2.5rem;
    width: 20rem;
    align-self: center;
    border-radius: 20px;
    font-size: 15px;
    font-weight: 700;
    text-align: center;
    border: 2px solid black;
  }

  .form {
    margin-bottom: 2rem;
  }

  .button-login {
    margin-top: 60px;
  }
</style>
