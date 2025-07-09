<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Countdown to Tomorrow 2 PM</title>
  <style>
    body {
      background: linear-gradient(135deg, #6a11cb, #2575fc);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }h1 {
  font-size: 3rem;
  margin-bottom: 30px;
  text-shadow: 2px 2px #00000030;
}

.countdown {
  display: flex;
  gap: 20px;
  font-size: 2.5rem;
  font-weight: bold;
  background: rgba(255, 255, 255, 0.1);
  padding: 20px 40px;
  border-radius: 20px;
  box-shadow: 0 0 15px rgba(0,0,0,0.4);
}

.countdown div {
  text-align: center;
}

.label {
  font-size: 0.8rem;
  font-weight: normal;
  opacity: 0.8;
}

  </style>
</head>
<body>
  <h1>Countdown to Tomorrow at 2:00 PM</h1>
  <div class="countdown" id="countdown">
    <div><span id="hours">00</span><div class="label">Hours</div></div>
    <div><span id="minutes">00</span><div class="label">Minutes</div></div>
    <div><span id="seconds">00</span><div class="label">Seconds</div></div>
  </div>  <script>
    function updateCountdown() {
      const now = new Date();
      const tomorrow = new Date();
      tomorrow.setDate(now.getDate() + 1);
      tomorrow.setHours(14, 0, 0, 0); // 2:00 PM tomorrow

      const diff = tomorrow - now;

      if (diff <= 0) {
        document.getElementById('countdown').innerHTML = '<div>Event Started</div>';
        return;
      }

      const hours = Math.floor(diff / (1000 * 60 * 60));
      const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((diff % (1000 * 60)) / 1000);

      document.getElementById('hours').textContent = String(hours).padStart(2, '0');
      document.getElementById('minutes').textContent = String(minutes).padStart(2, '0');
      document.getElementById('seconds').textContent = String(seconds).padStart(2, '0');
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script></body>
</html>
