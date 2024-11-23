<script>
  import Nav from "../../lib/Nav.svelte";
  import Footer from "../../lib/Footer.svelte";

  let accessKey = "";
  let errorMessage = "";

  function handleLogin() {
    if (accessKey === "examiscoming") {
      window.alert("Login successful! Redirecting...");
      window.location.href = "/love-assessor";
    } else {
      errorMessage = "Invalid key! Please try again.";
    }
  }

  function redirectToBuyAccessKey() {
    window.location.href = "/access-buy";
  }
</script>

<style>
  .login-container {
    text-align: center;
    padding: 6rem 2rem;
    background: linear-gradient(135deg, #ff4b47, #ffd700);
    color: white;
    min-height: 100vh;
  }

  .login-container h1 {
    font-size: 3rem;
    margin-bottom: 2rem;
    font-weight: 800;
  }

  .login-container input {
    padding: 1rem 2rem;
    font-size: 1.2rem;
    border-radius: 10px;
    border: none;
    margin-bottom: 1.5rem;
    background: rgba(255, 255, 255, 0.2);
    color: white;
    outline: none;
    transition: all 0.3s ease;
    width: 100%;
    max-width: 400px;
  }

  .login-container input:focus {
    background: rgba(255, 255, 255, 0.3);
    box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
  }

  .login-container button {
    padding: 1rem 2.5rem;
    font-size: 1.3rem;
    background: linear-gradient(90deg, #ffd700, #ff4b47);
    border: none;
    border-radius: 50px;
    color: white;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s ease;
    margin: 1rem 0;
  }

  .login-container button:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
  }

  .buy-key-button {
    background: linear-gradient(90deg, #ff4b47, #ff0000);
  }

  .error {
    color: #ff4b47;
    font-weight: bold;
    margin-top: 1rem;
  }
</style>

<Nav active="login" />

<div class="login-container">
  <h1>Login</h1>
  <input type="password" placeholder="Enter Access Key" bind:value={accessKey} />
  <br />
  <button on:click={handleLogin}>Submit</button>
  <button class="buy-key-button" on:click={redirectToBuyAccessKey}>Buy Access Key</button>
  {#if errorMessage}
    <p class="error">{errorMessage}</p>
  {/if}
</div>

<Footer />
