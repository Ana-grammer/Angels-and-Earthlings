# Angels-and-Earthlings
<!DOCTYPE html>
<html>
<head>
  <title>Colorful Spin Wheel</title>
  <style>
    /* Styles for the spinning wheel and hand */
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f0f0f0;
      font-family: Arial, sans-serif;
    }

    #wheel {
      width: 300px;
      height: 300px;
      border-radius: 50%;
      background-image: conic-gradient(#ff6f61, #ffa41b, #ffd500, #4caf50, #2196f3, #9c27b0, #ff6f61);
      position: relative;
      overflow: hidden;
      animation: spinWheel 3s ease-out forwards; /* Animation for spinning wheel */
    }

    @keyframes spinWheel {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(720deg); } /* Change the number of degrees for desired rotations */
    }

    #hand {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 24px;
      color: white;
      pointer-events: none;
    }

    #spinButton {
      padding: 10px 20px;
      margin-top: 20px;
      background-color: #333;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <div id="wheel">
    <div id="hand">👉</div>
  </div>
  
  <button id="spinButton" onclick="spinWheel()">Spin</button>

  <script>
    let isSpun = false; // Variable to track if wheel is already spun
    const names = ["Deborah", "Natasha", "Nicole", "Elizabeth", "Nikita", "Nathanial", "Nathan", "Nathius"]; // Add your list of names here
    const wheel = document.getElementById('wheel');
    const hand = document.getElementById('hand');
    const spinButton = document.getElementById('spinButton');

    function spinWheel() {
      if (!isSpun && names.length > 0) {
        // Disable spin button during animation
        spinButton.disabled = true;

        // Trigger the spinning animation
        wheel.style.animation = 'spinWheel 3s ease-out forwards';

        setTimeout(function() {
          const randomIndex = Math.floor(Math.random() * names.length);
          const selectedName = names[randomIndex];

          // Display selected name
          hand.textContent = selectedName;

          // Remove selected name from the list
          names.splice(randomIndex, 1);

          // Enable spin button after animation and reset wheel animation
          spinButton.disabled = false;
          wheel.style.animation = '';
        }, 5000); // 3 seconds

        isSpun = true; // Set to true after spinning
      } else if (names.length === 0) {
        alert("All names have been picked!");
      }
    }
  </script>

</body>
</html>

    
    
