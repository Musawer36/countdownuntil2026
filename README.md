# countdownuntil2026
A sleek countdown timer counting down to the year 2026
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Countdown to 2026</title>
  <style>
    body {
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      color: #f0f0f5;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      text-align: center;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 30px;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
    }
    #countdown {
      display: flex;
      gap: 20px;
      font-size: 2.5rem;
      font-weight: bold;
    }
    .time-section {
      background: rgba(255, 255, 255, 0.15);
      padding: 20px 30px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
      min-width: 90px;
    }
    .number {
      font-size: 3.5rem;
      color: #ffd700; /* Gold */
      text-shadow: 1px 1px 2px #000;
    }
    .label {
      font-size: 1rem;
      color: #d1d1d1;
      margin-top: 5px;
      text-transform: uppercase;
      letter-spacing: 1.5px;
    }
  </style>
</head>
<body>
  <h1>Countdown to 2026</h1>
  <div id="countdown">
    <div class="time-section">
      <div class="number" id="days">0</div>
      <div class="label">Days</div>
    </div>
    <div class="time-section">
      <div class="number" id="hours">0</div>
      <div class="label">Hours</div>
    </div>
    <div class="time-section">
      <div class="number" id="minutes">0</div>
      <div class="label">Minutes</div>
    </div>
    <div class="time-section">
      <div class="number" id="seconds">0</div>
      <div class="label">Seconds</div>
    </div>
  </div>

  <script>
    const countdownDate = new Date('January 1, 2026 00:00:00').getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const distance = countdownDate - now;

      if (distance <= 0) {
        document.getElementById('countdown').innerHTML = "<h2>Welcome to 2026! 🎉</h2>";
        clearInterval(interval);
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById('days').textContent = days;
      document.getElementById('hours').textContent = hours;
      document.getElementById('minutes').textContent = minutes;
      document.getElementById('seconds').textContent = seconds;
    }

    updateCountdown();
    const interval = setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
