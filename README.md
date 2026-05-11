<!doctype html>
<html>
<head>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700;900&display=swap" rel="stylesheet">
<style>
body{margin:0;font-family:Roboto,Arial,sans-serif;background:#fff;color:#210043;display:flex;align-items:center;justify-content:center;height:100vh;text-align:center}
h1{font-size:28px;margin:0 0 16px;font-weight:700}
#clock{font-size:52px;font-weight:900;letter-spacing:1px}
.seconds{color:#e61313}
.label{font-size:14px;margin-top:12px;opacity:.8}
</style>
</head>
<body>
<div>
  <h1>Countdown to September 7, 2026</h1>
  <div id="clock">Loading...</div>
  <div class="label">9:00 AM EDT</div>
</div>

<script>
const target = new Date("2026-09-07T09:00:00-04:00").getTime();

function updateCountdown(){
  const diff = target - Date.now();

  if(diff <= 0){
    document.getElementById("clock").innerHTML = "It’s time!";
    return;
  }

  const d = Math.floor(diff / 86400000);
  const h = Math.floor((diff % 86400000) / 3600000);
  const m = Math.floor((diff % 3600000) / 60000);
  const s = Math.floor((diff % 60000) / 1000);

  document.getElementById("clock").innerHTML =
    `${d}d ${h}h ${m}m <span class="seconds">${s}s</span>`;
}

updateCountdown();
setInterval(updateCountdown, 1000);
</script>
</body>
</html>
