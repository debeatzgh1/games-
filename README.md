<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Ghana Entertainment Games & Quizzes</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.1/dist/tailwind.min.css" rel="stylesheet">

<style>
body{background:#f3f4f6;font-family:system-ui}
.carousel{display:flex;gap:28px;overflow-x:auto;scroll-snap-type:x mandatory;padding:32px}
.card{min-width:340px;background:#fff;border-radius:20px;box-shadow:0 12px 30px rgba(0,0,0,.15);scroll-snap-align:center}
.timer{background:#14532d;color:#fff;padding:6px 14px;border-radius:999px;font-size:13px}
.btn{padding:10px;border-radius:14px;font-weight:600}
.play-btn{
 position:fixed;left:14px;top:50%;transform:translateY(-50%);
 background:#16a34a;color:#fff;padding:8px 14px;
 border-radius:12px;font-size:13px;font-weight:700;
 box-shadow:0 8px 22px rgba(0,0,0,.25);z-index:9999;cursor:pointer
}
.play-btn:hover{opacity:.9}
</style>
</head>

<body>

<!-- 🔊 Sounds -->
<audio id="clickSound" src="https://assets.mixkit.co/sfx/preview/mixkit-game-click-1114.mp3"></audio>
<audio id="correctSound" src="https://assets.mixkit.co/sfx/preview/mixkit-correct-answer-tone-2870.mp3"></audio>
<audio id="wrongSound" src="https://assets.mixkit.co/sfx/preview/mixkit-wrong-answer-fail-notification-946.mp3"></audio>
<audio id="finishSound" src="https://assets.mixkit.co/sfx/preview/mixkit-achievement-bell-600.mp3"></audio>

<div class="play-btn" onclick="document.getElementById('games').scrollIntoView({behavior:'smooth'})">
🎮 Play Games
</div>

<header class="text-center py-8">
<h1 class="text-3xl font-bold">🇬🇭 Ghana Entertainment Games Hub</h1>
<p class="text-gray-600 mt-2">Three fun quizzes for students & entertainment lovers</p>
</header>

<div id="games" class="carousel"></div>

<script>
const quizzes = [
{
 title:"🎵 Ghana Music & Celebrities",
 desc:"Artists, songs and awards",
 questions:[
  ["Sarkodie is a rapper from Ghana.",true],
  ["Shatta Wale is a gospel artist.",false],
  ["VGMA means Vodafone Ghana Music Awards.",true],
  ["Stonebwoy won a BET award.",true],
  ["Highlife music originated in Ghana.",true],
  ["Kidi is a footballer.",false],
  ["Black Sherif sang 'Kwaku the Traveller'.",true],
  ["R2Bees are comedians.",false],
  ["Reggie Rockstone pioneered Hiplife.",true],
  ["Efya is a male artist.",false],
  ["Yaw Tog is from Kumasi.",true],
  ["Dancehall is popular in Ghana.",true],
  ["King Promise won VGMA AOTY.",true],
  ["Gyakie sings Afrobeats.",true],
  ["Sarkodie never won awards.",false],
  ["Highlife uses live instruments.",true],
  ["Chalé means enemy.",false],
  ["Music is big in Ghana.",true],
  ["Local music goes international.",true],
  ["Hiplife mixes hip-hop & highlife.",true]
 ]
},
{
 title:"⚽ Ghana Sports & Movies",
 desc:"Sports legends & local films",
 questions:[
  ["Abedi Pele is a Ghanaian football legend.",true],
  ["Asamoah Gyan scored Ghana’s first World Cup goal.",true],
  ["Kotoko is a basketball club.",false],
  ["Black Stars represent Ghana.",true],
  ["Azonto is a movie genre.",false],
  ["Yvonne Nelson is an actress.",true],
  ["Majid Michel acts in Ghanaian movies.",true],
  ["Kumawood produces movies.",true],
  ["Michael Essien played for Chelsea.",true],
  ["Sports is unpopular in Ghana.",false],
  ["Nollywood is Ghanaian.",false],
  ["Football unites Ghanaians.",true],
  ["GH Premier League exists.",true],
  ["Movies influence culture.",true],
  ["Jackie Appiah is an actress.",true],
  ["Basketball is Ghana’s main sport.",false],
  ["Ghana hosted AFCON.",true],
  ["Sports create jobs.",true],
  ["Cinema is growing in Ghana.",true],
  ["Local films are globally streamed.",true]
 ]
},
{
 title:"🎉 Ghana Lifestyle & Fun Facts",
 desc:"Slang, culture and trends",
 questions:[
  ["‘Chop’ means eat in Ghana.",true],
  ["Jollof originated in Europe.",false],
  ["Accra is Ghana’s capital.",true],
  ["Kente is traditional cloth.",true],
  ["‘Chale’ means friend.",true],
  ["Azonto is a dance.",true],
  ["Waakye is a drink.",false],
  ["Tro-tro is public transport.",true],
  ["December is festival season.",true],
  ["Palm wine is popular.",true],
  ["Fufu is fast food.",false],
  ["Independence Day is March 6.",true],
  ["Ghana uses the Cedi.",true],
  ["Beaches are common.",true],
  ["Night markets are popular.",true],
  ["Street food is loved.",true],
  ["‘Bra’ means come.",true],
  ["Music influences fashion.",true],
  ["Hospitality is valued.",true],
  ["Tourism is growing.",true]
 ]
}
];

const container = document.getElementById("games");

function play(id){const s=document.getElementById(id);s.currentTime=0;s.play()}

quizzes.forEach((quiz,qi)=>{
 let index=0,score=0,time=10,timer;
 const card=document.createElement("div");
 card.className="card p-5";

 function render(){
  clearInterval(timer);time=10;
  card.innerHTML=`
   <h3 class="text-xl font-bold mb-1">${quiz.title}</h3>
   <p class="text-sm text-gray-600 mb-3">${quiz.desc}</p>
   <div class="flex justify-between mb-3">
    <span class="timer">⏱️ ${time}s</span>
    <span class="font-semibold">Score: ${score}</span>
   </div>
   <p class="font-semibold mb-4">${quiz.questions[index][0]}</p>
   <div class="grid grid-cols-2 gap-4">
    <button class="btn bg-green-700 text-white" id="t">TRUE</button>
    <button class="btn bg-emerald-600 text-white" id="f">FALSE</button>
   </div>
  `;
  card.querySelector("#t").onclick=()=>answer(true);
  card.querySelector("#f").onclick=()=>answer(false);
  timer=setInterval(()=>{
   time--;card.querySelector(".timer").innerText=`⏱️ ${time}s`;
   if(time<=0) next();
  },1000);
 }

 function answer(v){
  play("clickSound");
  if(v===quiz.questions[index][1]){score+=5;play("correctSound")}
  else play("wrongSound");
  next();
 }

 function next(){
  clearInterval(timer);index++;
  if(index<quiz.questions.length) render();
  else finish();
 }

 function finish(){
  play("finishSound");
  card.innerHTML=`
   <h3 class="text-xl font-bold mb-3">🎉 Quiz Completed!</h3>
   <p class="font-semibold mb-4">Score: ${score} / 100</p>
   <button class="btn bg-green-700 text-white w-full mb-3" onclick="location.reload()">🔁 Retake Quiz</button>
   <p class="text-center text-green-700 font-semibold">Thanks for playing 🇬🇭</p>
  `;
 }

 render();
 container.appendChild(card);
});
</script>

</body>
</html>
