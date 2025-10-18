<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rolador de Dados 🎲</title>
  <style>
    body {
      background-color: #222;
      color: #fff;
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    h1 {
      margin-bottom: 20px;
    }

    input, button {
      padding: 10px;
      margin: 5px;
      border: none;
      border-radius: 8px;
    }

    input {
      width: 80px;
      text-align: center;
    }

    button {
      background-color: #4CAF50;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #45a049;
    }

    #resultado {
      margin-top: 20px;
      font-size: 1.2em;
    }
  </style>
</head>
<body>

  <h1>🎲 Rolador de Dados 🎲</h1>
  <label for="qtdDados">Quantidade de dados:</label>
  <input type="number" id="qtdDados" min="1" value="1">
  <button id="rolar">Rolar!</button>

  <div id="resultado">Aguardando rolagem...</div>

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
