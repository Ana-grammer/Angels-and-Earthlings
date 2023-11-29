# Angels-and-Earthlings
<!DOCTYPE html>
<html>
<head>
  <title>Colorful Spin Wheel</title>
  <style>
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
    const names = ["Deborah", "Natasha", "Nicole", "Elizabeth", "Nikita", "Nathanial", "Nathan", "Nathius"]; // Add your list of names here
    const wheel = document.getElementById('wheel');
    const hand = document.getElementById('hand');

    function spinWheel() {
      if (names.length > 0) {
        const randomIndex = Math.floor(Math.random() * names.length);
        const selectedName = names[randomIndex];

        // Display selected name
        hand.textContent = selectedName;

        // Remove selected name from the list
        names.splice(randomIndex, 1);
      } else {
        alert("All names have been picked!");
      }
    }
  </script>

</body>
</html> 
