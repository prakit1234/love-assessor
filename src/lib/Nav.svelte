<script>
    export let active = ""; // To highlight the active section
  </script>
  
  <style>
    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      background: linear-gradient(to right, #ff6f61, #ff9f80);
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }
  
    nav ul {
      list-style: none;
      display: flex;
      gap: 1.5rem;
    }
  
    nav ul li {
      font-size: 1rem;
    }
  
    nav ul li a {
      text-decoration: none;
      color: white;
      font-weight: bold;
      transition: color 0.3s;
    }
  
    nav ul li a:hover,
    nav ul li a.active {
      color: #ffd700;
    }
  
    .logo {
      font-size: 1.5rem;
      font-weight: bold;
      color: white;
    }
  </style>
  
  <nav>
    <div class="logo">Love Assessor</div>
    <ul>
      <li><a href="/" class:active={active === "home"}>Home</a></li>
      <li><a href="#features" class:active={active === "features"}>Features</a></li>
      <li><a href="#faqs" class:active={active === "faqs"}>FAQs</a></li>
      <li><a href="#contact" class:active={active === "contact"}>Contact Us</a></li>
    </ul>
  </nav>
  