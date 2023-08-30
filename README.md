# Game Mario criado no p5.js 🎮

<li> O objetivo do jogo é levar o Mario até o castelo, posicionado em 512x512. Ao reinicar o jogo o player volta para o inicio da tela.

Utilizamos funções do p5.js para facilitar a criação, uma vez que essa foi a primeira aula prática do curso de desenvolvimento de software back-end

## Função de carregar imagens

// Executa apenas uma vez ao iniciar o programa
function setup() {
  createCanvas(576, 576);
  personagem = loadImage('mario2.png');
  castelo = loadImage('castelo1.png');
  grama = loadImage('grama1.jfif');
  
}

### Funções de loop para o personagem ganhar movimento

// fica executando em loop até o programa ser encerrado
function draw() {
  background(220);
  if (andarX < 0) {
    andarX = 0
  }
  if (andarX > tamanho * 8) {
    andarX = tamanho * 8
  }
  if (andarY < 0) {
    andarY = 0
  }
  if (andarY > tamanho * 8) {
    andarY = tamanho * 8
  }
  for (let x = 0; x < 9; x++) {
    for (let y = 0; y < 9; y++) {
      image(grama, tamanho * x, tamanho * y, tamanho, tamanho)
    }
    image(personagem, andarX, andarY, tamanho, tamanho)
    image(castelo, X=512, Y=512, tamanho, tamanho)

  }

### Função IF para a validação de posicionamento do personagem

  if (andarX === 512 && andarY === 512) {

    rect(160, 160, 256, 256)
    textSize(35)
    text('GANHOU!', 210, 240)
    restart = createButton('Reiniciar')
    restart.position(240, 350)
    restart.mousePressed(reseted)
    noLoop()
  }
}

function reseted() {
  andarX = 0
  andarY = 0
  restart.remove()
  loop()
}

### Por fim utilizamos a função keyPressed para o algoritmo captar a movimentação do personagem através as setas do teclado 
 
//executa uma vez a cada vez que uma tecla é pressionada

function keyPressed() {
  if (keyIsDown(DOWN_ARROW)) {
    andarY += velocidade
  }
  if (keyIsDown(UP_ARROW)) {
    andarY -= velocidade
  }
  if (keyIsDown(LEFT_ARROW)) {
    andarX -= velocidade
  }
  if (keyIsDown(RIGHT_ARROW)) {
    andarX += velocidade
  }
}

Você pode conferir todo o código do game no arquivo: game.js ou acessar direto na plataforma p5js, no endereço: https://editor.p5js.org/Ramon-DS/sketches/TWJ7mqHqf

</li>


![Start Game](https://editor.p5js.org/Ramon-DS/sketches/TWJ7mqHqf)

