<script lang="ts">
  import { scale } from "svelte/transition"; 
  import Heart from "../components/+page.svelte";

  let name1: string = "";
  let name2: string = "";
  let percentage: number = 0;
  let message: string = ""; 

  const predefinedPairs: Record<string, number> = {
    "PD|7 years old girls": 100,
    "Hidanshu|Ayesha": 100,
    "PD|Gay": 100,
     "Hidanshu|Andrew Tate": 100,
  };

  function calculateLove() {
    const key = `${name1}|${name2}`;
    const reversedKey = `${name2}|${name1}`;

    if (key in predefinedPairs) {
      percentage = predefinedPairs[key];
    } else if (reversedKey in predefinedPairs) {
      percentage = predefinedPairs[reversedKey];
    } else {
      percentage = Math.floor(Math.random() * 101);
    }

   
    if (percentage === 100) {
      message =
        "OMG! 100%? Your love is one in a million! Wishing you a lifetime of happiness and love. 💖";
    } else {
      message = ""; 
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
  <p class="percentage">{percentage}%</p>
  {#if message}
    <p class="message" in:scale>{message}</p> 
  {/if}
</div>

<style>
  
  .container {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fbc2eb);
    padding: 2rem;
    animation: fadeIn 1.5s ease-in-out;
  }

  
  h1 {
    font-size: 3rem;
    background: linear-gradient(to right, #ff758c, #ff7eb3);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 1.5rem;
    animation: pop 1s ease-out;
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
    transition: box-shadow 0.3s;
  }

  input:focus {
    outline: none;
    box-shadow: 0 0 10px #ff7eb3;
  }

  button {
    background: linear-gradient(to right, #ff758c, #ff7eb3);
    border: none;
    padding: 0.75rem 1.5rem;
    color: white;
    border-radius: 25px;
    cursor: pointer;
    font-size: 1.2rem;
    transition: transform 0.3s, background 0.3s;
  }

  button:hover {
    background: linear-gradient(to left, #ff758c, #ff7eb3);
    transform: scale(1.1);
  }

  
  .percentage {
    font-size: 2.5rem;
    color: #ff758c;
    font-weight: bold;
    animation: pop 0.6s ease-out;
  }

  
  .message {
    margin-top: 1.5rem;
    font-size: 1.5rem;
    color: #ff6b81;
    font-weight: bold;
    text-align: center;
    max-width: 400px;
    animation: pop 0.8s ease-out;
  }

  
  @keyframes pop {
    0% {
      transform: scale(0);
    }
    50% {
      transform: scale(1.2);
    }
    100% {
      transform: scale(1);
    }
  }

  @keyframes fadeIn {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
</style>
