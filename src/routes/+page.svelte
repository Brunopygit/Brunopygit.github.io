<style>
    .background {
        background-color: rgb(15, 15, 15); /* Cor de fundo escura */
        color: rgb(0, 0, 0); /* Cor do texto preta */
        font-family: Helvetica; /* Fonte para o texto */
        font-size: 20px; /* Tamanho do texto moderado */
        margin: 0;
        padding: 0;
        height: 93vh; /* Ocupa toda a altura da tela */
        display: flex;
        justify-content: center; /* Centraliza os itens horizontalmente */
        align-items: center; /* Alinha os itens no centro verticalmente */
        flex-direction: column;
        text-align: left; /* Garante que o texto esteja alinhado à esquerda dentro do container */
        padding-left: 20px; /* Adiciona espaçamento à esquerda */
    }

    .background p {
        background-color: rgb(255, 255, 255); /* Fundo branco atrás do texto */
        padding: 10px;
        border-radius: 5px;
        margin-bottom: 10px;
    }

    .background img {
        width: 300px; /* Define o tamanho médio da imagem */
        height: auto; /* Mantém a proporção da imagem */
        margin-left: auto; /* Empurra a imagem para a direita */
        margin-top: 20px;
    }
    .inscricao-button {
        margin-top: 10px;
    }
</style>

<div class="background">
    <p>Deseja ter um curso técnico e ser alguém de botar moral nesse mundão?</p>
    <p>Você chegou ao lugar certo, inscreva-se agora para a prova anual do IFMS.</p>
    <p>Clique no botão abaixo agora mesmo e seja FELIZ!</p>

    <img src="https://i.pinimg.com/originals/f3/f9/d4/f3f9d4e478e5d05bf16969bc551b3d45.gif" alt="Imagem animada">

    <!-- Botão inscreva-se -->
    <a href="https://brunopygit.github.io/login" class="btn btn-primary inscricao-button">Inscreva-se</a>
</div>
