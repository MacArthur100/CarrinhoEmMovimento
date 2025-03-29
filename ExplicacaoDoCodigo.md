Exercicio Prática de Desing 2º periodo -FATEC
Explicação do código

Vamos analisar o código HTML e JavaScript linha por linha para entender como ele funciona.
<!DOCTYPE html>
•	Informa ao navegador que o documento está em HTML5, o que ajuda na interpretação correta do conteúdo.
<html lang="PT-BR">
•	Abre a tag <html> e define o idioma do documento como português do Brasil (PT-BR).
<head>
•	Inicia a seção <head> do documento, onde são colocadas informações como metadados, título e estilos.
    <meta charset="UTF-8">
•	Define a codificação de caracteres do documento como UTF-8, permitindo o uso de caracteres especiais.
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
•	Especifica que a visualização deve se ajustar à largura da tela do dispositivo, útil para design responsivo.
    <title>Document</title>
•	Define o título do documento, que é exibido na aba do navegador.
    <style>
•	Inicia uma seção de estilo onde você pode definir CSS para estilizar o documento.
        body{
            overflow: hidden;
        }
•	Define que o elemento body não deve permitir rolagem, ocultando qualquer conteúdo que ultrapasse os limites da janela.
        #carro{
            /* a posição deve ser absoluta para animação ocorrer */
            position: absolute;
            left: 0;
        }
•	Estiliza o elemento com ID carro para que ele tenha uma posição absoluta, permitindo seu deslocamento na tela. O valor left: 0 posiciona o carro no canto esquerdo da tela.
    </style>
•	Fecha a seção <style>.
</head>
<body>
•	Fecha a seção <head> e inicia a seção <body>, que contém o conteúdo visível da página.
    <img id="carro" src="IMG/download.jfif" alt="isso é um carro">
•	Insere uma imagem com o ID carro, cujo caminho é IMG/download.jfif e o texto alternativo é "isso é um carro". Essa imagem representa o carro que se moverá na tela.
    <script>
•	Inicia um bloco de script JavaScript, onde você pode escrever código que adiciona interatividade à página.
        let posicaoDoCarrinho = 0;
•	Declara uma variável chamada posicaoDoCarrinho e inicializa seu valor como 0. Essa variável armazenará a posição atual do carro na tela.
        const carro = document.getElementById('carro');
•	Obtém o elemento com ID carro (a imagem do carro) e atribui à constante carro para que possa ser manipulada mais tarde no script.
        // criar uma função recursiva
•	Um comentário para indicar que a função que será definida a seguir é uma função recursiva.
        function moverCarro(){
•	Declara uma função chamada moverCarro que será responsável por mover a imagem do carro.
            if(posicaoDoCarrinho > window.innerWidth){
•	Verifica se a posicaoDoCarrinho é maior que a largura da janela do navegador.
                // ele reseta a posição do carrinho
                posicaoDoCarrinho = -100;
•	Se a posição do carro ultrapassar a largura da janela, a posição é redefinida para -100, colocando o carro fora da tela do lado esquerdo.
            }
•	Fecha a estrutura de controle if.
            // move o carrinho de 5 em 5 pixels
            posicaoDoCarrinho = posicaoDoCarrinho + 5;
•	Incrementa posicaoDoCarrinho em 5, movendo o carro para a direita a cada chamada da função.
            carro.style.left = posicaoDoCarrinho + "px";
•	Atualiza a propriedade left do estilo do carro, movendo-o para a nova posição calculada.
        }
•	Fecha a função moverCarro.
        setInterval(moverCarro, 30);
•	Chama a função moverCarro a cada 30 milissegundos, o que cria uma animação contínua do carro se movendo pela tela.
    </script>
</body>
</html>
•	Fecha a tag <script>, o corpo do documento e a tag <html>.
Resumo
Esse código cria uma animação simples em que uma imagem de carro se move da esquerda para a direita na tela, reiniciando sua posição assim que sai da tela. O uso de setInterval garante que a função de movimento seja chamada repetidamente, proporcionando a animação.
