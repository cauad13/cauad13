<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Impostos</title>
</head>
<body>
    <h1>Calculadora de Impostos</h1>

    <label for="productId">ID do Produto:</label>
    <input type="text" id="productId" placeholder="Insira o ID do produto">

    <button onclick="calcularImpostos()">Calcular Impostos</button>

    <div id="resultado"></div>

    <script>
        function calcularImpostos() {
            // Recuperar o ID do produto do campo de entrada
            const productId = document.getElementById('productId').value;

            // Enviar o ID do produto para o servidor (back-end) para calcular impostos usando uma API de IA

            // Exemplo: supondo que você use o fetch para enviar uma solicitação ao back-end
            fetch(`/api/calcular-impostos?productId=${productId}`)
                .then(response => response.json())
                .then(data => {
                    // Exibir o resultado no elemento 'resultado'
                    document.getElementById('resultado').innerText = `Impostos calculados: ${data.impostos}`;
                })
                .catch(error => console.error('Erro ao calcular impostos:', error));
        }
    </script>
</body>
</html>
