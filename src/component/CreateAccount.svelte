<script>
  import ComLogo from "../image/Hardwarelogo.png";
</script>

<main>
  <div class="signUpForm">
    <img src={ComLogo} alt="Hardware Logo" />

    <section>
      <form action="">
        <section>
          <label for="fullname">FullName</label>
          <input type="text" class="signin-input" required />
        </section>

        <section>
          <label for="id">Employee-ID</label>
          <input type="text" class="signin-input" required />
        </section>

        <section>
          <label for="password">Password</label>
          <input type="text" class="signin-input" required />
        </section>
      </form>

      <section>
        <button>Create new account</button>
      </section>
    </section>
  </div>
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
  }
</style>
