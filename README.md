<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>2026 Countdown</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      background: transparent;
      font-family: -apple-system, BlinkMacSystemFont, "Inter", sans-serif;
      color: #000;
    }
    .wrap {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 12px;
    }
    .percent {
      font-size: 28px;
      font-weight: 600;
    }
    .label {
      font-size: 12px;
      opacity: 0.6;
      margin-top: 4px;
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="percent" id="progress">—</div>
    <div class="label">of 2026 completed</div>
  </div>

  <script>
    const start = new Date("2026-01-01T00:00:00Z").getTime();
    const end   = new Date("2026-12-31T23:59:59Z").getTime();
    const now   = Date.now();

    const progress = Math.min(
      Math.max((now - start) / (end - start), 0),
      1
    );

    document.getElementById("progress").textContent =
      Math.round(progress * 100) + "%";
  </script>
</body>
</html>
