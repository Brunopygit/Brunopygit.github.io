<script>
    let nome_usuario = '', senha_usuario = '', autenticado = false;
    let usuarios = {};
    let data_nascimento_string = '';

    function calcular_idade() {
        const hj = new Date(), nascimento = new Date(data_nascimento_string);
        let idade = hj.getFullYear() - nascimento.getFullYear();
        const mes = hj.getMonth() - nascimento.getMonth();
        if (mes < 0 || (mes === 0 && hj.getDate() < nascimento.getDate())) idade--;
        return idade;
    }

    function registrar_usuario() {
        nome_usuario = document.getElementById('nome_usuario').value;
        senha_usuario = document.getElementById('senha_usuario').value;
        data_nascimento_string = document.getElementById('data_nascimento').value;

        if (nome_usuario && senha_usuario && data_nascimento_string) {
            const idade = calcular_idade();
            if (idade >= 12) {
                if (!usuarios[nome_usuario]) {
                    usuarios[nome_usuario] = senha_usuario;
                    autenticado = true;
                    alert("Usuário registrado com sucesso!");
                    document.getElementById('nome_usuario').value = '';
                    document.getElementById('senha_usuario').value = '';
                    document.getElementById('data_nascimento').value = '';
                } else {
                    alert("Usuário já existe.");
                }
            } else {
                alert("Você precisa ter 12 anos ou mais para se registrar.");
            }
        } else {
            alert("Por favor, preencha todos os campos.");
        }
    }

    function autenticar_usuario() {
        nome_usuario = document.getElementById('nome_usuario').value;
        senha_usuario = document.getElementById('senha_usuario').value;

        if (usuarios[nome_usuario] && usuarios[nome_usuario] === senha_usuario) {
            autenticado = true;
            alert("Usuário autenticado com sucesso!");
            document.getElementById('nome_usuario').value = '';
            document.getElementById('senha_usuario').value = '';
        } else {
            alert("Nome de usuário ou senha incorretos.");
        }
    }

    function desautenticar_usuario() {
        autenticado = false;
        alert("Você saiu da conta.");
    }

    function excluir_usuario() {
        if (confirm("Tem certeza que deseja excluir a conta?")) {
            delete usuarios[nome_usuario];
            autenticado = false;
            alert("Conta excluída com sucesso.");
        }
    }

    function horario() {
        const horaatual = new Date().getHours();
        if (horaatual >= 6 && horaatual < 12) {
            return "Bom dia";
        } else if (horaatual >= 12 && horaatual < 18) {
            return "Boa tarde";
        } else {
            return "Boa noite";
        }
    }
</script>

<style>
    /* Importando a fonte "Poppins" */
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');

    /* Estilos para o container principal */
    .page-container {
        background-color: rgb(15, 15, 15); /* Cor de fundo */
        color: rgb(255, 255, 255); /* Cor do texto */
        font-family: 'Poppins', sans-serif; /* Fonte mais destacada */
        font-size: 16px; /* Tamanho do texto */
        margin: 0;
        padding: 0;
        height: 100vh; /* Ocupa toda a altura da tela */
        display: flex;
        flex-direction: column;
        justify-content: center; /* Centraliza o conteúdo verticalmente */
        align-items: center; /* Alinha o conteúdo horizontalmente */
    }

    /* Estilos para o conteúdo principal (container) */
    .container {
        background-color: white; /* Fundo branco */
        color: rgb(0, 0, 0); /* Texto preto para contraste */
        padding: 30px; /* Maior espaçamento interno */
        width: 500px; /* Largura fixa */
        border-radius: 20px; /* Bordas arredondadas */
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra para destaque */
        margin: 20px auto;
        text-align: center; /* Centraliza o texto */
    }

    /* Estilos para os botões */
    button {
        margin: 10px;
        padding: 10px 20px;
        background-color: rgb(252, 248, 51); /* Cor do botão */
        color: black;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-weight: bold; /* Deixa o texto dos botões em negrito */
    }

    button:hover {
        background-color: rgb(251, 255, 0); /* Tom mais escuro ao passar o mouse */
    }

    /* Estilos para os inputs */
    input {
        padding: 10px;
        margin: 15px 0;
        font-size: 16px;
        width: 100%; /* Largura total */
        border: 1px solid #ccc;
        border-radius: 5px;
        display: block;
        box-sizing: border-box; /* Garante que o padding não afete a largura */
    }

    /* Tornar o texto mais destacado e em negrito */
    .container p {
        font-weight: bold;
        font-size: 18px; /* Aumenta o tamanho do texto */
    }
</style>

<!-- Conteúdo principal -->
<div class="page-container">
    <h1 style="text-align: center;">BEM VINDO</h1>
    <div class="container">
        {#if !autenticado}
            <p>PREENCHA TODOS OS CAMPOS:</p>
            NOME: <input type="text" id="nome_usuario" /><br />
            SENHA: <input type="password" id="senha_usuario" /><br />
            DATA DE NASCIMENTO: <input type="date" id="data_nascimento" /><br />
            <button on:click={registrar_usuario}>SIGN UP</button>
            <button on:click={autenticar_usuario}>LOGIN</button>
        {:else}
            <p>{horario()}, bem-vindo(a) {nome_usuario}, você tem {calcular_idade()} anos</p>
            <button on:click={excluir_usuario}>Excluir conta</button>
            <button on:click={desautenticar_usuario}>Sair da conta</button>
        {/if}
    </div>
</div>
