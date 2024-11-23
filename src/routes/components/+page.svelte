<script>
    export let percentage = 0;
  </script>
  
  <div class="heart-container">
    <div class="heart">
      <div class="liquid" style="height: {percentage}%"></div>
    </div>
  </div>
  
  <style>
    .heart-container {
      position: relative;
      width: 150px;
      height: 150px;
      margin: 1rem auto;
    }
  
    .heart {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #ffccd5;
      clip-path: polygon(50% 0%, 100% 40%, 80% 100%, 50% 80%, 20% 100%, 0% 40%);
      overflow: hidden;
      border: 2px solid #ff758c;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
  
    .liquid {
      position: absolute;
      bottom: 0;
      width: 100%;
      background: #ff758c;
      transition: height 1s ease-in-out;
    }
  </style>
  