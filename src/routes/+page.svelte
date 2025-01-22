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
    body {
      background-color: blue;
    }
  </style>
  
 
  <body>

  <center>
  {#if !autenticado}
    <p>Preencha os campos:</p>
    <p>Site teste, exercício 02 de dw4.</p>
    Nome do usuário: <input type="text" id="nome_usuario" /><br />
    <p></p>
    Senha: <input type="password" id="senha_usuario" /><br />
    <p></p>
    Data de nascimento: <input type="date" id="data_nascimento" /><br />
    <p></p>
    <p></p>
    <button onclick={registrar_usuario}>Registrar usuário</button>
    <button onclick={autenticar_usuario}>Autenticar usuário</button>
  {:else}
    <p>{horario()}, bem-vindo(a) {nome_usuario}, você tem {calcular_idade()} anos</p>
    <button onclick={excluir_usuario}>Excluir conta</button>
    <button onclick={desautenticar_usuario}>Sair da conta</button>
  {/if}
  </center>

</body>
  