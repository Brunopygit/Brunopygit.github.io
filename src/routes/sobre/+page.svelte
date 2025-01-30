<script>
    function redirectToStore() {
        // Redirecionar para a página da loja
        window.location.href = "https://brunopygit.github.io/receitas";
    }
</script>

<style>
    /* Estilos específicos para esta página */
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
    }

    /* Container centralizado */
    .container {
        text-align: center;
        background-color: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    h1 {
        font-size: 2.5rem;
        color: rgb(0, 0, 0);
        margin-bottom: 20px;
    }

    .mid-text {
        font-size: 1.5rem;
        color: rgb(0, 0, 0);
        margin-top: 40px;
    }

    .store-button {
        background-color: rgb(0, 123, 255);
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        font-size: 1rem;
        cursor: pointer;
        margin-top: 20px;
    }

    .store-button:hover {
        background-color: rgb(0, 86, 179);
    }

    /* Cor de fundo específica para esta página */
    body.specific-page {
        background-color: rgb(173, 216, 230); /* Azul claro */
        height: 100vh;
    }
</style>

<!-- Adicione a classe 'specific-page' ao body desta página -->
<body class="specific-page">
    <div class="container">
        <h1>Venha fazer parte da família Wanderson Fit, estamos ansiosos pela sua participação, bora pro treino !</h1>
        <div class="mid-text">
            Acesse aqui a nossa loja e venha ficar grandão:
        </div>
        <button class="store-button" onclick="redirectToStore()">Ir para a Loja</button>
    </div>
</body>