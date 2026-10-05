<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,user-scalable=no">
<meta name="theme-color" content="#111111">
<title>Run Blaze 🔥🏃</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
  user-select:none;
  -webkit-user-select:none;
}

html,body{
  width:100%;
  height:100%;
  overflow:hidden;
  background:#111;
  font-family:Arial,sans-serif;
}

#game{
  position:relative;
  width:100%;
  height:100%;
  max-width:600px;
  margin:auto;
  overflow:hidden;
  background:linear-gradient(#55b8ff,#dff6ff);
}

/* Road */
#road{
  position:absolute;
  left:10%;
  width:80%;
  height:100%;
  background:#303030;
  border-left:6px solid #fff;
  border-right:6px solid #fff;
}

.lane{
  position:absolute;
  top:-100px;
  width:8px;
  height:100px;
  background:#fff;
  left:33.33%;
  transform:translateX(-50%);
}

.lane2{
  position:absolute;
  top:-100px;
  width:8px;
  height:100px;
  background:#fff;
  left:66.66%;
  transform:translateX(-50%);
}

/* Player */
#player{
  position:absolute;
  width:58px;
  height:78px;
  bottom:105px;
  left:50%;
  transform:translateX(-50%);
  z-index:5;
  font-size:50px;
  text-align:center;
  line-height:78px;
}

/* Objects */
.object{
  position:absolute;
  z-index:4;
  text-align:center;
  font-size:42px;
}

.obstacle{
  width:55px;
  height:55px;
}

.coin{
  width:45px;
  height:45px;
}

.power{
  width:52px;
  height:52px;
}

/* HUD */
#hud{
  position:absolute;
  top:15px;
  left:15px;
  right:15px;
  z-index:20;
  display:flex;
  justify-content:space-between;
  color:#fff;
  font-size:18px;
  font-weight:bold;
  text-shadow:2px 2px 3px #000;
}

.hudBox{
  background:rgba(0,0,0,.45);
  padding:8px 12px;
  border-radius:15px;
}

/* Start / Game Over */
.screen{
  position:absolute;
  inset:0;
  z-index:30;
  background:rgba(0,0,0,.78);
  color:white;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:25px;
}

.screen h1{
  font-size:48px;
  margin-bottom:15px;
}

.screen p{
  font-size:19px;
  margin:7px;
}

button{
  margin-top:25px;
  padding:15px 35px;
  border:0;
  border-radius:30px;
  background:#ff5722;
  color:#fff;
  font-size:20px;
  font-weight:bold;
  cursor:pointer;
}

button:active{
  transform:scale(.95);
}

#gameover{
  display:none;
}

/* Controls */
#controls{
  position:absolute;
  bottom:15px;
  left:0;
  right:0;
  z-index:20;
  display:flex;
  justify-content:space-between;
  padding:0 20px;
}

.control{
  width:85px;
  height:65px;
  border-radius:20px;
  border:2px solid rgba(255,255,255,.5);
  background:rgba(255,255,255,.25);
  color:white;
  font-size:32px;
  display:flex;
  align-items:center;
  justify-content:center;
  touch-action:none;
}

#boost{
  position:absolute;
  bottom:20px;
  left:50%;
  transform:translateX(-50%);
  z-index:25;
  width:70px;
  height:70px;
  border-radius:50%;
  background:#ff9800;
  border:3px solid white;
  color:white;
  font-size:28px;
  display:none;
}
</style>
</head>

<body>

<div id="game">

  <div id="road">
    <div class="lane"></div>
    <div class="lane2"></div>
  </div>

  <div id="hud">
    <div class="hudBox">🔥 Score: <span id="score">0</span></div>
    <div class="hudBox">🪙 <span id="coins">0</span></div>
  </div>

  <div id="player">🏃</div>

  <div id="controls">
    <div class="control" id="left">⬅️</div>
    <div class="control" id="right">➡️</div>
  </div>

  <div id="boost">⚡</div>

  <div id="start" class="screen">
    <h1>🔥 Run Blaze</h1>
    <p>🏃 Run as far as you can!</p>
    <p>🪙 Collect coins</p>
    <p>🧲 Magnet collects nearby coins</p>
    <p>⚡ Boost gives extra speed</p>
    <p>🚧 Avoid the obstacles</p>
    <button id="startButton">START GAME</button>
  </div>

  <div id="gameover" class="screen">
    <h1>💥 Game Over</h1>
    <p>Your Score: <b id="finalScore">0</b></p>
    <p>🪙 Coins: <b id="finalCoins">0</b></p>
    <button id="restartButton">PLAY AGAIN</button>
  </div>

</div>

<script>
const game = document.getElementById("game");
const player = document.getElementById("player");
const scoreText = document.getElementById("score");
const coinsText = document.getElementById("coins");
const startScreen = document.getElementById("start");
const gameOverScreen = document.getElementById("gameover");
const finalScore = document.getElementById("finalScore");
const finalCoins = document.getElementById("finalCoins");

let running = false;
let score = 0;
let coins = 0;
let speed = 5;
let playerLane = 1;
let objects = [];
let lastTime = 0;
let spawnTimer = 0;
let animationId = null;

const lanes = [25,50,75];

function setPlayerLane(){
  player.style.left = lanes[playerLane] + "%";
}

function createObject(type){
  const obj = document.createElement("div");
  obj.className = "object " + type;

  if(type === "obstacle"){
    obj.textContent = ["🚧","🪨","🚙"][Math.floor(Math.random()*3)];
  }

  if(type === "coin"){
    obj.textContent = "🪙";
  }

  if(type === "magnet"){
    obj.textContent = "🧲";
  }

  if(type === "boost"){
    obj.textContent = "⚡";
  }

  const lane = Math.floor(Math.random()*3);
  obj.dataset.lane = lane;
  obj.style.left = lanes[lane] + "%";
  obj.style.transform = "translateX(-50%)";
  obj.style.top = "-70px";

  game.appendChild(obj);

  objects.push({
    el:obj,
    lane:lane,
    y:-70,
    type:type
  });
}

function spawnObject(){
  const random = Math.random();

  if(random < 0.60){
    createObject("obstacle");
  }else if(random < 0.86){
    createObject("coin");
  }else if(random < 0.94){
    createObject("magnet");
  }else{
    createObject("boost");
  }
}

function hitTest(a,b){
  const ar = a.getBoundingClientRect();
  const br = b.getBoundingClientRect();

  return !(
    ar.right < br.left ||
    ar.left > br.right ||
    ar.bottom < br.top ||
    ar.top > br.bottom
  );
}

function removeObject(index){
  if(objects[index] && objects[index].el){
    objects[index].el.remove();
  }
  objects.splice(index,1);
}

function endGame(){
  running = false;

  if(animationId){
    cancelAnimationFrame(animationId);
  }

  finalScore.textContent = Math.floor(score);
  finalCoins.textContent = coins;
  gameOverScreen.style.display = "flex";
}

function gameLoop(time){
  if(!running) return;

  const delta = Math.min(time-lastTime,40);
  lastTime = time;

  score += delta * 0.015;
  scoreText.textContent = Math.floor(score);

  spawnTimer += delta;

  if(spawnTimer > 750){
    spawnObject();
    spawnTimer = 0;
  }

  for(let i=objects.length-1;i>=0;i--){
    const o = objects[i];

    o.y += speed * delta / 16;
    o.el.style.top = o.y + "px";

    if(
      o.type === "coin" &&
      o.lane === playerLane &&
      Math.abs(o.y - (game.clientHeight-160)) < 70
    ){
      coins++;
      coinsText.textContent = coins;
      removeObject(i);
      continue;
    }

    if(
      o.type === "magnet" &&
      o.lane === playerLane &&
      Math.abs(o.y - (game.clientHeight-160)) < 70
    ){
      removeObject(i);

      objects.forEach(item=>{
        if(item.type === "coin"){
          item.lane = playerLane;
          item.el.style.left = lanes[playerLane] + "%";
        }
      });

      continue;
    }

    if(
      o.type === "boost" &&
      o.lane === playerLane &&
      Math.abs(o.y - (game.clientHeight-160)) < 70
    ){
      speed = Math.min(speed + 3,12);
      removeObject(i);
      continue;
    }

    if(
      o.type === "obstacle" &&
      o.lane === playerLane &&
      hitTest(player,o.el)
    ){
      endGame();
      return;
    }

    if(o.y > game.clientHeight + 80){
      removeObject(i);
    }
  }

  speed += delta * 0.00015;
  speed = Math.min(speed,10);

  animationId = requestAnimationFrame(gameLoop);
}

function startGame(){
  objects.forEach(o=>{
    if(o.el) o.el.remove();
  });

  objects = [];
  score = 0;
  coins = 0;
  speed = 5;
  playerLane = 1;

  scoreText.textContent = "0";
  coinsText.textContent = "0";

  setPlayerLane();

  startScreen.style.display = "none";
  gameOverScreen.style.display = "none";

  running = true;
  lastTime = performance.now();
  spawnTimer = 0;

  animationId = requestAnimationFrame(gameLoop);
}

function moveLeft(){
  if(!running) return;

  if(playerLane > 0){
    playerLane--;
