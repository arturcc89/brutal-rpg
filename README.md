<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RPG de Terror - Rolagem de Dados</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #1b1b1b;
      color: #f5f5f5;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      background-color: #ff0000;
      color: white;
      border: none;
      border-radius: 5px;
    }
    input {
      width: 50px;
      font-size: 16px;
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>RPG de Terror - Rolagem de Dados</h1>
  
  <label>Quantos lados? </label>
  <input type="number" id="sides" value="6" min="2">
  
  <label>Quantos dados? </label>
  <input type="number" id="amount" value="1" min="1">
  
  <button onclick="rollDice()">Rolar Dados</button>
  
  <h2 id="result">Resultado: -</h2>
  
  <button onclick="sendWhatsApp()">Enviar para WhatsApp</button>
  
  <script>
    let lastRoll = "";

    function rollDice() {
      const sides = parseInt(document.getElementById('sides').value);
      const amount = parseInt(document.getElementById('amount').value);
      const results = [];
      for(let i=0; i<amount; i++){
        results.push(Math.floor(Math.random() * sides) + 1);
      }
      lastRoll = results.join(', ');
      document.getElementById('result').innerText = "Resultado: " + lastRoll;
    }

    function sendWhatsApp() {
      if(!lastRoll){
        alert("Role os dados primeiro!");
        return;
      }
      const phone = "5531998199329"; // seu número com código do Brasil
      const message = encodeURIComponent("Resultado da rolagem: " + lastRoll);
      window.open(https://api.whatsapp.com/send?phone=${phone}&text=${message}, "_blank");
    }
  </script>
</body>
</html>
