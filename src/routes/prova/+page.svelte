<script>
    import { questionario } from "$lib/questionario";
    let promise = $state();
    let respostas = $state([]);
    let respondeu = $state(false);
    let mensagemResultado = $state(""); // Variável para armazenar a mensagem

    function verificarRespostas() {
        respondeu = true;
        let acertos = 0;
        for (let i = 0; i < questionario.length; i++) {
            if (respostas[i] === questionario[i].correct_answer) {
                acertos++;
            }
        }
        
        // Lógica para determinar a mensagem com base no número de acertos
        if (acertos >= 14) {
            mensagemResultado = "Parabéns você passou na prova do IFMS";
        } else if (acertos >= 11 && acertos <= 13) {
            mensagemResultado = "Infelizmente você ficou para a segunda chamada.";
        } else {
            mensagemResultado = "Infelizmente você não passou no IFMS, mais sorte da próxima vez..";
        }

        // Exibir o número de acertos
        alert(`Você acertou ${acertos} de ${questionario.length} questões!`);
    }
</script>

<div class="container">
    <ol>
        {#each questionario as pergunta, i}
            <h4><li>{@html pergunta.question}</li></h4>
            {#each pergunta.answers as alternativa}
                <div class="form-check">
                    <input class="form-check-input" type="radio" id={alternativa} bind:group={respostas[i]} value={alternativa} oninput={() => (respondeu = false)} />
                    <label class="form-check-label" for={alternativa}>{@html alternativa}</label>

                    {#if respondeu && alternativa == respostas[i]}
                        {#if alternativa == pergunta.correct_answer}
                            <span class="badge bg-success">Correto</span>
                        {:else}
                            <span class="badge bg-danger">Incorreto</span>
                        {/if}
                    {/if}
                </div>
            {/each}
        {/each}
    </ol>
    <button onclick={verificarRespostas} class="btn btn-success">Confirmar!</button>
    <!-- Exibir a mensagem após a verificação -->
    {#if respondeu}
        <div class="alert alert-info mt-4">
            <p>{@html mensagemResultado}</p>
        </div>
    {/if}
</div>
