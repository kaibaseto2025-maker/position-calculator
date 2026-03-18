<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Position Size Calculator</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #020617, #0f172a);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.container {
  width: 90%;
  max-width: 420px;
  background: #1e293b;
  padding: 25px;
  border-radius: 18px;
  box-shadow: 0 10px 40px rgba(0,0,0,0.7);
  text-align: center;
}

h1 {
  margin-bottom: 5px;
}

p {
  color: #94a3b8;
  margin-bottom: 20px;
}

input {
  width: 100%;
  padding: 14px;
  margin: 10px 0;
  border: none;
  border-radius: 10px;
  font-size: 16px;
  outline: none;
}

button {
  width: 100%;
  padding: 14px;
  background: linear-gradient(135deg, #22c55e, #16a34a);
  border: none;
  border-radius: 10px;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  transform: scale(1.03);
}

.result {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
  opacity: 0;
  transform: translateY(10px);
  transition: 0.3s;
}

.result.show {
  opacity: 1;
  transform: translateY(0);
}

.details {
  margin-top: 10px;
  font-size: 14px;
  color: #cbd5f5;
}
</style>
</head>

<body>

<div class="container">
  <h1>Position Size Calculator</h1>
  <p>Manage your risk like a pro 📊</p>

  <input type="number" id="balance" placeholder="Account Balance ($)">
  <input type="number" id="risk" placeholder="Risk per trade (%)">
  <input type="number" id="stoploss" placeholder="Stop Loss (pips / %)">

  <button onclick="calculate()">Calculate</button>

  <div class="result" id="result"></div>
  <div class="details" id="details"></div>
</div>

<script>
function calculate() {
  let balance = parseFloat(document.getElementById("balance").value);
  let risk = parseFloat(document.getElementById("risk").value);
  let stoploss = parseFloat(document.getElementById("stoploss").value);

  let resultEl = document.getElementById("result");
  let detailsEl = document.getElementById("details");

  if (isNaN(balance) || isNaN(risk) || isNaN(stoploss) || stoploss === 0) {
    resultEl.innerText = "Fill all fields correctly 😑";
    resultEl.classList.add("show");
    detailsEl.innerText = "";
    return;
  }

  let riskAmount = (balance * risk) / 100;
  let positionSize = riskAmount / stoploss;

  resultEl.innerText = `Position Size: ${positionSize.toFixed(2)}`;
  detailsEl.innerText = `Risk Amount: $${riskAmount.toFixed(2)}`;

  resultEl.classList.remove("show");
  void resultEl.offsetWidth;
  resultEl.classList.add("show");
}
</script>

</body>
</html>
