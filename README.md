<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rolar Dados 🎲</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #20232a;
      color: #fff;
      margin-top: 100px;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
      border-radius: 10px;
      border: none;
    }
    button {
      background-color: #61dafb;
      color: #000;
      cursor: pointer;
    }
    button:hover {
      background-color: #21a1f1;
    }
    #resultado {
      font-size: 24px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>🎲 Rolar Dados 🎲</h1>
  <p>Escolha quantos dados deseja rolar:</p>
  <input type="number" id="qtdDados" min="1" value="1">
  <button id="rolar">Rolar</button>
  <div id="resultado"></div>

  <script>
    const botao = document.getElementById("rolar");
    const resultadoDiv = document.getElementById("resultado");

    botao.addEventListener("click", () => {
      const qtd = parseInt(document.getElementById("qtdDados").value) || 1;
      const resultados = [];

      for (let i = 0; i < qtd; i++) {
        resultados.push(Math.floor(Math.random() * 6) + 1);
      }

      resultadoDiv.innerHTML = 🎲 Resultado: [${resultados.join(", ")}];
    });
  </script>
</body>
</html>
