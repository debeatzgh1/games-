<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Ghana Entertainment Games Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.1/dist/tailwind.min.css" rel="stylesheet">

<style>
body { background:#f3f4f6; font-family: system-ui; }

/* Floating Play Button */
.play-btn{
  position:fixed;
  left:12px;
  top:50%;
  transform:translateY(-50%);
  background:#16a34a;
  color:#fff;
  padding:8px 14px;
  border-radius:10px;
  font-weight:700;
  font-size:13px;
  box-shadow:0 6px 20px rgba(0,0,0,.25);
  cursor:pointer;
  z-index:9999;
}
.play-btn:hover{opacity:.9}

/* Carousel */
.carousel{
  display:flex;
  overflow-x:auto;
  scroll-snap-type:x mandatory;
  gap:24px;
  padding:30px;
}
.card{
  min-width:340px;
  background:#fff;
  border-radius:18px;
  box-shadow:0 10px 25px rgba(0,0,0,.15);
  scroll-snap-align:center;
}
.timer{
  background:#14532d;
  color:#fff;
  padding:6px 12px;
  border-radius:999px;
  font-size:13px;
}
.btn{
  padding:10px;
  border-radius:12px;
  font-weight:600;
  cursor:pointer;
}
</style>
</head>

<body>

<!-- 🔊 Sounds -->
<audio id="clickSound" src="https://assets.mixkit.co/sfx/preview/mixkit-game-click-1114.mp3"></audio>
<audio id="correctSound" src="https://assets.mixkit.co/sfx/preview/mixkit-correct-answer-tone-2870.mp3"></audio>
<audio id="wrongSound" src="https://assets.mixkit.co/sfx/preview/mixkit-wrong-answer-fail-notification-946.mp3"></audio>
<audio id="finishSound" src="https://assets.mixkit.co/sfx/preview/mixkit-achievement-bell-600.mp3"></audio>

<div class="play-btn" onclick="scrollToGames()">🎮 Play Games</div>

<header class="text-center py-8">
  <h1 class="text-3xl font-bold">🇬🇭 Ghana Entertainment Games Hub</h1>
  <p class="text-gray-600 mt-2">Fun quizzes for students & entertainment lovers</p>
</header>

<div id="games" class="carousel"></div>

<script>
const quizzes = [
{
  title:"🎵 Ghana Music & Celebrities Quiz",
  desc:"Test your knowledge of Ghanaian music & stars",
  questions:[
    ["Sarkodie is a rapper from Ghana.",true],
    ["Shatta Wale is a gospel musician.",false],
    ["VGMA means Vodafone Ghana Music Awards.",true],
    ["Stonebwoy won a BET award.",true],
    ["Highlife music started in Ghana.",true],
    ["Kidi is a footballer.",false],
    ["Black Sherif sang 'Kwaku the Traveller'.",true],
    ["R2Bees are comedians.",false],
    ["Reggie Rockstone pioneered Hiplife.",true],
    ["Efya is a male artist.",false],
    ["Kumerica refers to Kumasi culture.",true],
    ["Yaw Tog is a gospel singer.",false],
    ["Dancehall is popular in Ghana.",true],
    ["King Promise won VGMA AOTY.",true],
    ["Gyakie sings Afrobeats.",true],
    ["Sarkodie never won awards.",false],
    ["Highlife uses live instruments.",true],
    ["Chalé means enemy.",false],
    ["Music is big in Ghana.",true],
    ["Local music goes international.",true]
  ]
}
];

const container = document.getElementById("games");

function playSound(id){
  const s = document.getElementById(id);
  s.currentTime = 0;
  s.play();
}

quizzes.forEach((quiz, quizIndex)=>{
  let qIndex = 0;
  let score = 0;
  let time = 10;
  let timer;

  const card = document.createElement("div");
  card.className = "card p-5";

  function renderQuestion(){
    clearInterval(timer);
    time = 10;

    card.innerHTML = `
      <h3 class="text-xl font-bold mb-2">${quiz.title}</h3>
      <p class="text-sm text-gray-600 mb-3">${quiz.desc}</p>

      <div class="flex justify-between mb-3">
        <span class="timer">⏱️ ${time}s</span>
        <span class="font-semibold">Score: ${score}</span>
      </div>

      <p class="font-semibold mb-4">${quiz.questions[qIndex][0]}</p>

      <div class="grid grid-cols-2 gap-4">
        <button id="trueBtn" class="btn bg-green-700 text-white hover:bg-green-800">TRUE</button>
        <button id="falseBtn" class="btn bg-emerald-600 text-white hover:bg-emerald-700">FALSE</button>
      </div>
    `;

    card.querySelector("#trueBtn").onclick = ()=>handleAnswer(true);
    card.querySelector("#falseBtn").onclick = ()=>handleAnswer(false);

    timer = setInterval(()=>{
      time--;
      card.querySelector(".timer").innerText = `⏱️ ${time}s`;
      if(time <= 0) nextQuestion();
    },1000);
  }

  function handleAnswer(value){
    playSound("clickSound");
    if(value === quiz.questions[qIndex][1]){
      score += 5;
      playSound("correctSound");
    } else {
      playSound("wrongSound");
    }
    nextQuestion();
  }

  function nextQuestion(){
    clearInterval(timer);
    qIndex++;
    if(qIndex < quiz.questions.length){
      renderQuestion();
    } else {
      playSound("finishSound");
      card.innerHTML = `
        <h3 class="text-xl font-bold mb-3">🎉 Quiz Completed!</h3>
        <p class="font-semibold mb-4">Final Score: ${score} / 100</p>

        <button class="btn bg-green-700 text-white w-full mb-3" onclick="location.reload()">🔁 Retake Quiz</button>
        <p class="text-center text-green-700 font-semibold">Thanks for playing 🇬🇭</p>
      `;
    }
  }

  renderQuestion();
  container.appendChild(card);
});

function scrollToGames(){
  playSound("clickSound");
  document.getElementById("games").scrollIntoView({behavior:"smooth"});
}
</script>

</body>
</html>
