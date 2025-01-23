<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Curso Técnico</title>
    <!-- Incluindo o Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KyZXEJ03R8cO2Pk0M8t72hPRpHiM0G0s16b1FQxnDhTcPxRNh17XBpoWPC1hjTf4j" crossorigin="anonymous">
    <style>
        .background {
            background-color: rgb(15, 15, 15); /* Cor de fundo escura */
            color: rgb(255, 255, 255); /* Cor do texto */
            font-family: Helvetica; /* Fonte para o texto */
            font-size: 20px; /* Tamanho do texto moderado */
            margin: 0;
            padding: 0;
            height: 93vh; /* Ocupa toda a altura da tela */
            display: flex;
            justify-content: flex-start; /* Alinha os itens à esquerda */
            align-items: center; /* Alinha os itens no centro verticalmente */
            flex-direction: column;
        }

        .background p {
            margin-left: 20px; /* Adiciona espaço à esquerda do texto */
            background-color: rgb(255, 255, 255); /* Fundo branco atrás do texto */
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        .background img {
            width: 300px; /* Define o tamanho médio da imagem */
            height: auto; /* Mantém a proporção da imagem */
            margin-left: auto; /* Empurra a imagem para a direita */
        }

        .Logoif {
            margin: 0;
            width: 200px; /* Ajusta o tamanho da logo */
            height: auto;
            margin-left: auto;
            margin-right: auto;
            margin-top: 20px; /* Espaçamento do topo */
        }

        .inscricao-button {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div class="Logoif">
        <img src="https://i.ytimg.com/vi/hUo04TlPVRA/maxresdefault.jpg" alt="Logo">
    </div>

    <div class="background">
        <p>Deseja ter um curso técnico e ser alguém de botar moral nesse mundão?</p>
        <p>Você chegou ao lugar certo, inscreva-se agora para a prova anual do IFMS.</p>
        <p>Clique no botão abaixo agora mesmo e seja FELIZ!</p>

        <img src="https://i.pinimg.com/originals/f3/f9/d4/f3f9d4e478e5d05bf16969bc551b3d45.gif" alt="Imagem animada">

        <!-- Botão inscreva-se -->
        <a href="https://brunopygit.github.io/receitas" class="btn btn-primary inscricao-button">Inscreva-se</a>
    </div>

    <!-- Incluindo o Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js" integrity="sha384-oBqDVmMz4fnFO9gybfi7eJz5n4n2dBzZ5/K1q9mlnL07l3J7bE9Gr6n6nqZT7k5J" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.min.js" integrity="sha384-pzjw8f+ua7Kw1TIq0pHk46GRjXczv5cIcFfZd5b7gZ2eSw2gmc6uMZfTp8Bqpo0g" crossorigin="anonymous"></script>
</body>
</html>
