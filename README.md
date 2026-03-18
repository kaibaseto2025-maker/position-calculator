<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Trading Position Size Calculator – Calculate Risk Per Trade</title>
<meta name="description" content="Easily calculate your trading position size based on your account balance, risk %, and stop loss. Free online tool.">

<!-- Google AdSense -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-5540302661584443"
     crossorigin="anonymous"></script>

<style>
body{
font-family: Arial;
background:#0f172a;
color:white;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

.card{
background:#1e293b;
padding:25px;
border-radius:12px;
width:300px;
text-align:center;
}

input{
width:100%;
padding:10px;
margin:8px 0;
border-radius:6px;
border:none;
}

button{
background:#22c55e;
border:none;
padding:10px;
width:100%;
border-radius:6px;
font-weight:bold;
cursor:pointer;
}

.result{
margin-top:15px;
font-size:18px;
color:#38bdf8;
}
</style>
</head>

<body>

<div class="card">

<h2>Position Size Calculator</h2>

<input id="balance" placeholder="Account Balance ($)">
<input id="risk" placeholder="Risk % per trade">
<input id="stop" placeholder="Stop Loss (pips)">

<button onclick="calculate()">Calculate</button>

<div class="result" id="output"></div>

</div>

<script>

function calculate(){

let balance = document.getElementById("balance").value;
let risk = document.getElementById("risk").value;
let stop = document.getElementById("stop").value;

let riskMoney = balance * (risk/100);
let position = riskMoney / stop;

document.getElementById("output").innerText =
"Lot Size: " + position.toFixed(2);

}

</script>

</bod
</html>
