<script>
  import Nav from "../lib/Nav.svelte";
  import Footer from "../lib/Footer.svelte";
  import { goto } from '$app/navigation';
</script>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(to bottom, #ff9f80, #ff6f61, #ff4b47);
    color: #333;
    scroll-behavior: smooth;
    overflow-x: hidden;
  }

  .hero {
    text-align: center;
    padding: 6rem 2rem;
    background: linear-gradient(135deg, #ff6f61, #ff4b47);
    color: white;
    clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
    animation: fadeIn 1.5s ease-in-out;
  }

  @keyframes fadeIn {
    0% {
      opacity: 0;
      transform: translateY(-20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .hero h1 {
    font-size: 4rem;
    font-weight: 800;
    margin-bottom: 1.5rem;
    line-height: 1.2;
    text-shadow: 3px 3px 12px rgba(0, 0, 0, 0.3);
  }

  .hero p {
    font-size: 1.5rem;
    margin-bottom: 3rem;
    font-weight: 500;
    max-width: 750px;
    margin: 0 auto;
    text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.2);
  }

  .hero button {
    padding: 1.2rem 3rem;
    font-size: 1.3rem;
    background: linear-gradient(90deg, #ffd700, #ff4b47);
    border: none;
    border-radius: 50px;
    color: white;
    font-weight: bold;
    cursor: pointer;
    box-shadow: 0 12px 25px rgba(0, 0, 0, 0.4);
    transition: all 0.4s ease;
  }

  .hero button:hover {
    background: linear-gradient(90deg, #ff4b47, #ffd700);
    transform: scale(1.1);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5);
  }

  .sections {
    margin: 4rem 0;
  }

  .section {
    padding: 4rem 2rem;
    background: white;
    border-radius: 15px;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    margin: 2rem auto;
    max-width: 1200px;
    text-align: center;
  }

  .section h2 {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    color: #ff4b47;
  }

  .section p {
    font-size: 1.2rem;
    line-height: 1.8;
    color: #555;
  }
</style>

<Nav active="home" />

<div class="hero">
  <h1>Welcome to Love Assessor</h1>
  <p>Discover the chemistry between two people with fun and style. Let’s see how much they vibe!</p>
  <button on:click={() => goto('/login')}>Get Started</button>
</div>

<div class="sections">
  <div class="section">
    <h2>Features</h2>
    <p>Our Love Assessor provides a fun and interactive way to test compatibility.</p>
  </div>
  <div class="section">
    <h2>FAQs</h2>
    <p>Have questions? Check out our Frequently Asked Questions to learn more.</p>
  </div>
  <div class="section">
    <h2>Contact Us</h2>
    <p>Feel free to reach out at <a href="mailto:prakitchetia@gmail.com">Prakit chetia🥶</a>.</p>
  </div>
</div>

<Footer />
