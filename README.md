<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulário de Automação de Saneamento</title>
</head>
<body>
    <h1>Formulário de Automação de Saneamento</h1>
    <form id="formulario">
        <label for="gruposBombas">Grupos de Bombas:</label>
        <input type="number" id="gruposBombas" name="gruposBombas" required>
        <br><br>

        <div id="gruposDetails"></div>

        <button type="submit">Enviar</button>
    </form>

    <script>
        document.getElementById('gruposBombas').addEventListener('input', function() {
            const grupos = document.getElementById('gruposBombas').value;
            const gruposDetails = document.getElementById('gruposDetails');
            gruposDetails.innerHTML = '';

            for (let i = 1; i <= grupos; i++) {
                gruposDetails.innerHTML += `
                    <label for="bombasGrupo${i}">Quantidade de Bombas no Grupo ${i}:</label>
                    <input type="number" id="bombasGrupo${i}" name="bombasGrupo${i}" required>
                    <br><br>
                `;
            }
        });

        document.getElementById('formulario').addEventListener('submit', function(e) {
            e.preventDefault();
            // Aqui você pode pegar os dados e enviar para o backend
            alert("Formulário enviado!");
        });
    </script>
</body>
</html>
