<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aventura Interativa</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="game-container">
    <h1>Aventura na Floresta Encantada</h1>
    <p id="story-text">Você está na entrada de uma floresta misteriosa. Há dois caminhos à sua frente: um caminho iluminado e outro escuro e sinuoso.</p>
    <div id="choices">
      <button onclick="choosePath('illuminated')">Caminho Iluminado</button>
      <button onclick="choosePath('dark')">Caminho Escuro</button>
    </div>
  </div>
  
  <script src="script.js"></script>
</body>
</html>



SCRIPT.JS
let storyText = document.getElementById("story-text");
let choices = document.getElementById("choices");

function choosePath(path) {
  if (path === 'illuminated') {
    storyText.innerHTML = "Você segue pelo caminho iluminado e encontra um grupo de fadas que oferecem ajuda. Você aceita?";
    choices.innerHTML = `
      <button onclick="acceptFairies()">Aceitar Ajuda</button>
      <button onclick="declineFairies()">Recusar Ajuda</button>
    `;
  } else if (path === 'dark') {
    storyText.innerHTML = "Você entra pelo caminho escuro e ouve um som estranho. Algo está se aproximando.";
    choices.innerHTML = `
      <button onclick="investigateSound()">Investigar o Som</button>
      <button onclick="runAway()">Correr para Trás</button>
    `;
  }
}

function acceptFairies() {
  storyText.innerHTML = "As fadas oferecem uma poção mágica que te dá poderes especiais. Você agora pode explorar a floresta com segurança.";
  choices.innerHTML = "<button onclick='restartGame()'>Recomeçar Aventura</button>";
}

function declineFairies() {
  storyText.innerHTML = "Você recusa a ajuda das fadas e continua sua jornada sozinho. Em pouco tempo, você encontra uma clareira.";
  choices.innerHTML = "<button onclick='restartGame()'>Recomeçar Aventura</button>";
}

function investigateSound() {
  storyText.innerHTML = "Você se aproxima cautelosamente e descobre uma criatura mística que se revela amigável. Ela te guia até um tesouro escondido.";
  choices.innerHTML = "<button onclick='restartGame()'>Recomeçar Aventura</button>";
}

function runAway() {
  storyText.innerHTML = "Você corre de volta para a entrada da floresta, mas se arrepende de não ter enfrentado o perigo. Aventura encerrada.";
  choices.innerHTML = "<button onclick='restartGame()'>Recomeçar Aventura</button>";
}

function restartGame() {
  storyText.innerHTML = "Você está na entrada de uma floresta misteriosa. Há dois caminhos à sua frente: um caminho iluminado e outro escuro e sinuoso.";
  choices.innerHTML = `
    <button onclick="choosePath('illuminated')">Caminho Iluminado</button>
    <button onclick="choosePath('dark')">Caminho Escuro</button>
  `;
}


STYLE.CSS
 {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    font-family: 'Arial', sans-serif;
    background-color: #f0f8ff;
    color: #333;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }
  
  #game-container {
    text-align: center;
    background-color: white;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
    max-width: 600px;
    width: 100%;
  }
  
  h1 {
    color: #4CAF50;
  }
  
  button {
    background-color: #4CAF50;
    color: white;
    padding: 15px 30px;
    border: none;
    border-radius: 5px;
    margin: 10px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease;
  }
  
  button:hover {
    background-color: #45a049;
  }
  
  #choices {
    margin-top: 20px;
  }
