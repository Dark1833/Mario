<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Jogo do Mário</title>
</head>
<body>

<canvas id="canvas" width="400" height="400"></canvas>

<script>

const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");

// Variáveis do jogo
let mario = {
    x: 200,
    y: 200,
    width: 50,
    height: 50,
    velocidade: 5
};

// Função para desenhar o Mário
function desenharMario() {
    ctx.fillStyle = "red";
    ctx.fillRect(mario.x, mario.y, mario.width, mario.height);
}

// Função para mover o Mário
function moverMario() {
    mario.x += mario.velocidade;
    if (mario.x > canvas.width - mario.width) {
        mario.x = 0;
    }
}

// Função para iniciar o jogo
function iniciarJogo() {
    // Cria um intervalo para chamar a função de movimento
    setInterval(moverMario, 10);
}

// Chama a função para desenhar o Mário
desenharMario();

// Chama a função para iniciar o jogo
iniciarJogo();

</script>

</body>
</html>
