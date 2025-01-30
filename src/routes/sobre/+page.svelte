<script>
    // Função para navegar para a loja (em uma aplicação real, você pode configurar o roteamento com o svelte-router)
    function irParaLoja() {
        window.location.href = "/loja"; // Aqui você redireciona para a página de loja
    }
</script>

<style>
    /* Estilos globais */
    body {
        margin: 0;
        padding: 0;
        font-family: 'Poppins', sans-serif; /* Fonte moderna e grossa */
        background-color: rgb(160, 212, 229); /* Azul claro */
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    /* Estilo do título principal */
    h1 {
        font-size: 50px;
        font-weight: 700; /* Letras grossas */
        text-align: center;
        color: #333;
        margin-top: 50px;
        text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
        padding: 20px;
    }

    /* Estilo para o quadrado branco de destaque */
    .text-box {
        background-color: white; /* Fundo branco */
        padding: 30px;
        border-radius: 15px; /* Bordas arredondadas */
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        width: 80%;
        max-width: 600px;
        text-align: center;
    }

    /* Estilo da segunda frase */
    .sub-title {
        font-size: 24px;
        font-weight: 600; /* Negrito */
        color: #333;
        margin-bottom: 20px;
    }

    /* Estilo do botão */
    button {
        background-color: rgb(252, 248, 51); /* Cor do botão */
        color: black;
        font-size: 18px;
        font-weight: 700;
        padding: 15px 30px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }

    button:hover {
        background-color: rgb(251, 255, 0); /* Tom mais escuro ao passar o mouse */
    }
</style>

<!-- Corpo da página home -->
<div>
    <!-- Texto principal (capa da página) -->
    <h1>Venha fazer parte da família Wanderson Fit, estamos ansiosos pela sua participação, bora pro treino!</h1>

    <!-- Caixa de texto para a segunda frase -->
    <div class="text-box">
        <p class="sub-title">Acesse aqui a nossa loja e venha ficar grandão :</p>
        <button on:click={irParaLoja}>Ir para a loja</button>
    </div>
</div>
