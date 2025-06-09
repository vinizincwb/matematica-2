<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista com Botões RGB Automáticos</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        h1 {
            font-size: 96px; /* Tamanho maior para o título */
            margin-bottom: 60px;
            color: #333;
            text-align: center;
            font-weight: bold;
            text-transform: uppercase; /* Torna o texto maiúsculo */
        }

        .lista-botoes {
            display: flex; /* Flexbox para alinhamento horizontal */
            gap: 40px; /* Maior espaço entre os botões */
        }

        .botao-rgb {
            padding: 40px 80px; /* Botões bem grandes */
            font-size: 36px; /* Tamanho de fonte grande */
            border: 10px solid transparent; /* Aumenta a espessura da borda para 10px */
            background-color: black; /* Fundo preto */
            color: white;
            text-align: center;
            border-radius: 10px;
            transition: border-color 0.3s; /* Transição para a borda */
            min-width: 250px; /* Garantir que os botões fiquem grandes o suficiente */
        }

        .botao-rgb:hover {
            opacity: 0.8;
        }
    </style>
</head>
<body>

    <h1>Lista</h1> <!-- Título bem maior "Lista" -->

    <div class="lista-botoes">
        <button class="botao-rgb">Botão 1</button>
        <button class="botao-rgb">Botão 2</button>
    </div>

    <script>
        function mudarCorDeTodos() {
            // Gera uma cor RGB mais vibrante (garante maior saturação)
            const r = Math.floor(Math.random() * 156) + 100;  // Garante que o valor de r seja entre 100 e 255
            const g = Math.floor(Math.random() * 156) + 100;  // Garante que o valor de g seja entre 100 e 255
            const b = Math.floor(Math.random() * 156) + 100;  // Garante que o valor de b seja entre 100 e 255
            const corRGB = `rgb(${r}, ${g}, ${b})`;

            // Aplica a cor RGB à borda de todos os botões
            const botoes = document.querySelectorAll('.botao-rgb');
            botoes.forEach(botao => {
                botao.style.borderColor = corRGB; // Aplica a cor na borda
            });
        }

        // Altera a cor das bordas de todos os botões a cada 200 milissegundos (0.2s) para desacelerar
        setInterval(mudarCorDeTodos, 200); // Mudança mais suave
    </script>

</body>
</html>
