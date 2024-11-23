<script>
    let discordContact = "xtro_kai"; // Replace with your Discord username
    let emailContact = "bharsatnorah@gmail.com"; // Replace with your email
    let robloxGamepassLink = "https://www.roblox.com/game-pass/975048452/accesskey"; // Replace with your Roblox gamepass URL
  </script>
  
  <style>
    .access-buy-container {
      text-align: center;
      padding: 6rem 2rem;
      background: linear-gradient(135deg, #0078ff, #00ffcc);
      color: white;
      min-height: 100vh;
    }
  
    .access-buy-container h1 {
      font-size: 3rem;
      margin-bottom: 2rem;
      font-weight: 800;
    }
  
    .options {
      display: flex;
      flex-direction: column;
      gap: 2rem;
      align-items: center;
      justify-content: center;
    }
  
    .option {
      background: rgba(255, 255, 255, 0.1);
      padding: 2rem;
      border-radius: 20px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      width: 90%;
      max-width: 500px;
      text-align: center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
  
    .option:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
    }
  
    .option h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
      font-weight: bold;
      color: #ffcc00;
    }
  
    .option p {
      font-size: 1.2rem;
      margin-bottom: 1.5rem;
      color: #ffffff;
    }
  
    .option a {
      display: inline-block;
      padding: 1rem 2rem;
      font-size: 1.2rem;
      color: white;
      background: linear-gradient(90deg, #ff4b47, #ffcc00);
      text-decoration: none;
      border-radius: 30px;
      font-weight: bold;
      transition: all 0.3s ease;
    }
  
    .option a:hover {
      background: linear-gradient(90deg, #ffcc00, #ff4b47);
      transform: scale(1.05);
    }
  </style>
  
  <div class="access-buy-container">
    <h1>Buy Access Key</h1>
    <div class="options">
      <!-- Robux Purchase Option -->
      <div class="option">
        <h2>Buy with Robux</h2>
        <p>Purchase the key by buying my Roblox gamepass.</p>
        <a href={robloxGamepassLink} target="_blank">Buy Gamepass</a>
      </div>
  
      <!-- Contact Option -->
      <div class="option">
        <h2>Contact Me</h2>
        <p>
          If you'd prefer to pay directly, contact me through Discord or email:
        </p>
        <p><strong>Discord:</strong> {discordContact}</p>
        <p><strong>Email:</strong> {emailContact}</p>
      </div>
    </div>
  </div>
  

  