<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NSC - Network Speed Checker</title>
  
  <style>
    /* Light Mode Styles */
    body.light-mode {
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
      color: #333;
    }

    /* Dark Mode Styles */
    body.dark-mode {
      font-family: Arial, sans-serif;
      background-color: #333;
      color: #fff;
    }

    .container {
      text-align: center;
      margin-top: 50px;
    }

    button {
      padding: 10px 20px;
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 16px;
    }

    button:hover {
      background-color: #45a049;
    }

    .mode-switch {
      margin-top: 20px;
    }

    .hidden {
      display: none;
    }
  </style>

</head>
<body class="light-mode">
  <div class="container">
    <h1>NSC - Network Speed Checker</h1>
    <div id="speed-result">
      <p>Speed: <span id="speed-value">Loading...</span> Mbps</p>
    </div>
    <button id="check-speed-btn">Check Speed</button>
    <div class="mode-switch">
      <button id="toggle-theme">Switch to Dark Mode</button>
    </div>
    <div id="loading" class="hidden">Loading...</div>
  </div>

  <script>
    // Toggle between Dark and Light mode
    const themeButton = document.getElementById('toggle-theme');
    const body = document.body;

    themeButton.addEventListener('click', () => {
      if (body.classList.contains('light-mode')) {
        body.classList.remove('light-mode');
        body.classList.add('dark-mode');
        themeButton.innerText = 'Switch to Light Mode';
      } else {
        body.classList.remove('dark-mode');
        body.classList.add('light-mode');
        themeButton.innerText = 'Switch to Dark Mode';
      }
    });

    // Simulate Speed Test
    document.getElementById('check-speed-btn').addEventListener('click', () => {
      const loadingMessage = document.getElementById('loading');
      loadingMessage.classList.remove('hidden');
      document.getElementById('speed-value').innerText = 'Calculating...';

      // Simulate the speed test by generating a random speed value
      setTimeout(() => {
        const speed = (Math.random() * (100 - 5) + 5).toFixed(2); // Random speed between 5 and 100 Mbps
        document.getElementById('speed-value').innerText = speed;
        loadingMessage.classList.add('hidden');
      }, 2000); // Simulate a 2 second loading time
    });
  </script>
</body>
</html>
