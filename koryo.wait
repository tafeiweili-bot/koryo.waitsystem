<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>待ち時間 表示</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      font-family: "Segoe UI", sans-serif;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      background-image: linear-gradient(
          rgba(255,255,255,0.3),
          rgba(255,255,255,0.3)
        ),
        url("https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1950&q=80");
      background-size: cover;
      background-position: center;
    }

    .panel {
      background: rgba(0,0,0,0.25);
      padding: 50px 70px;
      border-radius: 25px;
      text-align: center;
      backdrop-filter: blur(10px);
    }

    .time {
      font-size: 72px;
      font-weight: bold;
      margin: 20px 0;
    }

    .status {
      font-size: 28px;
      margin-top: 10px;
      font-weight: bold;
    }

    .footer {
      position: fixed;
      left: 20px;
      bottom: 20px;
      font-size: 14px;
      opacity: 0.8;
      line-height: 1.5;
    }
  </style>
</head>
<body>

  <div class="panel">
    <h1>現在の待ち時間</h1>
    <div class="time" id="time">-- 分</div>
    <div class="status" id="status">---</div>
  </div>

  <div class="footer" id="footer">
    最終更新：--  
    <br>
    30分おきに更新されます
  </div>

  <script>
    const statusColors = {
      low: "#4caf50",  // 緑
      mid: "#ffeb3b",  // 黄
      high: "#f44336"  // 赤
    };

    const statusTexts = {
      low: "空いています",
      mid: "やや混雑しています",
      high: "混雑しています"
    };

    function update() {
      const minutes = localStorage.getItem("waitTime");
      const status = localStorage.getItem("status");
      const updated = localStorage.getItem("updated");

      if (minutes !== null) {
        document.getElementById("time").textContent = minutes + " 分";
      }

      if (status) {
        const statusEl = document.getElementById("status");
        statusEl.textContent = statusTexts[status];
        statusEl.style.color = statusColors[status];
      }

      if (updated) {
        document.getElementById("footer").innerHTML =
          "最終更新：" + updated + "<br>30分おきに更新されます";
      }
    }

    // 1秒ごとにチェックして反映
    setInterval(update, 1000);
    update();
  </script>

</body>
</html>
