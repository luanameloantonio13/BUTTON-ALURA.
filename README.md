# BUTTON-ALURA.
Nossa intenção era que apenas o elemento "ativo" fosse visível agora e, ao clicar em "Rio de Janeiro", fosse direcionado para nossa segunda div. No entanto, vamos necessitar de suporte do nosso CSS. É por meio dele que faremos as transições de exibição e ocultação das nossas divs. 

🗺️ Cidade Perdida - Jornada InterativaProjeto de um jogo interativo em texto onde suas escolhas determinam o próximo passo da aventura em busca de uma cidade perdida.🕹️ Dinâmica do JogoPasso 0 (Início): Exibe a carta antiga encontrada na biblioteca. O jogador deve escolher entre ir para o Rio de Janeiro ou para Pernambuco.Ocultar/Exibir: Ao clicar na opção do Rio de Janeiro (ou Pernambuco), o passo atual é ocultado e o próximo passo torna-se ativo.🛠️ Códigos Utilizados1. index.html (Estrutura)Adicione a classe ativo ao lado da classe passo dentro da tag <main> para definir o estado inicial do jogo:html<!-- código omitido -->
<main>
    <div class="passo ativo" id="passo-0">
        <p>Um dia desses, dentro de um livro da biblioteca da escola, eu descobri uma carta antiga sobre uma cidade perdida, escondida por riquezas e belezas naturais. Nessa carta, a autora deixa algumas pistas para encontrar essa cidade e eu decidi segui-las!</p>
        <button class="btn-proximo" data-proximo="1">Rio de Janeiro</button>
        <button class="btn-proximo" data-proximo="2">Pernambuco</button>
    </div>
    
    <div class="passo" id="passo-1">
        <p>Você começa sua jornada no Rio de Janeiro, subindo o Pico da Tijuca ao amanhecer para encontrar a primeira pista.</p>
        <button class="btn-proximo" data-proximo="3">Procurar a pista no topo do pico</button>
        <button class="btn-proximo" data-proximo="4">Desistir e voltar para casa</button>
    </div>
</main>
<!-- código omitido -->
Use o código com cuidado.2. script.js (Lógica e Interatividade)Para fazer os botões funcionarem e avançarem os passos, configure a constante avanca e selecione todos os botões:javascriptconst avanca = document.querySelectorAll('.btn-proximo');

avanca.forEach(button => {
    button.addEventListener('click', function(){
        const atual = document.querySelector('.ativo');
        const proximoPasso = 'passo-' + this.getAttribute('data-proximo');

        atual.classList.remove('ativo');
        document.getElementById(proximoPasso).classList.add('ativo');
    })
})
Use o código com cuidado.
