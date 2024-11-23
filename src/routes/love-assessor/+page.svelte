<script lang="ts">
  import Heart from "../components/+page.svelte";

  let name1: string = "";
  let name2: string = "";
  let percentage: number = 0;

  // Predefined pairs (case-sensitive comparison)
  const predefinedPairs: Record<string, number> = {
    "PD|VD": 100,
    "Hidanshu|Hidanshu's Princess": 100,
    "PD|Gay": 100,
  };

  function calculateLove() {
    // Create the key for comparison (case-sensitive matching)
    const key = `${name1}|${name2}`;
    const reversedKey = `${name2}|${name1}`; // Also check reversed order

    if (key in predefinedPairs) {
      percentage = predefinedPairs[key];
    } else if (reversedKey in predefinedPairs) {
      percentage = predefinedPairs[reversedKey];
    } else {
      percentage = Math.floor(Math.random() * 101); // Random percentage for other pairs
    }
  }
</script>


<div class="container">
  <h1>Love Assessor ❤️</h1>
  <div class="form">
    <input bind:value={name1} placeholder="Enter first name" />
    <input bind:value={name2} placeholder="Enter second name" />
    <button on:click={calculateLove}>Test Our Love</button>
  </div>
  <Heart percentage={percentage} />
  <p>{percentage}%</p>
</div>

<style>
  .container {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: linear-gradient(120deg, #ff9a9e, #fad0c4, #fbc2eb);
    padding: 2rem;
  }

  h1 {
    font-size: 3rem;
    background: linear-gradient(to right, #ff758c, #ff7eb3);
    -webkit-background-clip: text;
    background-clip: text; /* Added standard property */
    -webkit-text-fill-color: transparent;
    margin-bottom: 1.5rem;
  }

  .form {
    margin-bottom: 2rem;
  }

  input {
    margin: 0.5rem;
    padding: 0.75rem 1rem;
    border: 2px solid #fbc2eb;
    border-radius: 5px;
    font-size: 1rem;
    width: 250px;
  }

  button {
    background: linear-gradient(to right, #ff758c, #ff7eb3);
    border: none;
    padding: 0.75rem 1.5rem;
    color: white;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
    transition: background 0.3s;
    margin-top: 1rem;
  }

  button:hover {
    background: linear-gradient(to left, #ff758c, #ff7eb3);
  }

  p {
    font-size: 2rem;
    color: #ff758c;
  }
</style>
