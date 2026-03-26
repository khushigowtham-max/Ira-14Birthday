<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
    font-family:'Poppins',sans-serif;
    color:white;
    text-align:center;
    background:url("bg1.jpg") center/cover no-repeat fixed;
}

/* overlay */
body::before{
    content:"";
    position:fixed;
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.65);
    top:0;
    left:0;
    z-index:-1;
}

/* sections */
section{
    height:100vh;
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    padding:20px;
    opacity:0;
    transition:1s;
}
section.active{display:flex;opacity:1;}
#lock{display:flex;opacity:1;}

/* text */
h1{
    font-family:'Great Vibes',cursive;
    font-size:3.5em;
}
p{
    font-size:1.2em;
    max-width:600px;
    line-height:1.8;
}

/* button */
button{
    margin-top:20px;
    padding:12px 25px;
    border-radius:25px;
    border:none;
    background:white;
    color:black;
    cursor:pointer;
}

/* media */
.photo{
    width:250px;
    border-radius:15px;
    margin-top:20px;
    display:none;
}
video{
    width:300px;
    border-radius:15px;
    margin-top:20px;
}

/* chat */
.chatbox{width:300px;text-align:left;}
.msg{padding:10px;margin:10px;border-radius:15px;max-width:70%;}
.left{background:#222;}
.right{background:#0b93f6;margin-left:auto;}
</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
<h1>This is not just a website</h1>
<p>It is something I made for you</p>
<input type="password" id="pass">
<p style="opacity:0.7;">Hint: Who is better for Akanksha over Yogesh??</p>
<button onclick="check()">Enter</button>
</section>

<!-- MAIN -->
<div id="main" style="display:none;">

<section id="s1">
<h1 id="typing"></h1>
<button onclick="next('s2')">keep going</button>
</section>

<section id="s2">
<p>I don’t think I ever said this properly<br>So I made this instead</p>
<button onclick="reveal('m1')">tap to reveal</button>
<img src="Ira3.jpg" id="m1" class="photo">
<button onclick="next('s3')">there’s more</button>
</section>

<section id="s3">
<p>You didn’t change my life all at once<br>It happened slowly</p>
<button onclick="reveal('m2')">tap to reveal</button>
<img src="Ira1.jpg" id="m2" class="photo">
<button onclick="next('s4')">wait</button>
</section>

<section id="s4">
<p>These moments meant more than I ever said</p>
<video controls>
<source src="Ira Video.mp4" type="video/mp4">
</video>
<button onclick="next('s5')">one more</button>
</section>

<section id="s5">
<p>You became the person I go to without thinking</p>
<button onclick="reveal('m3')">tap to reveal</button>
<img src="Ira2.jpg" id="m3" class="photo">
<button onclick="next('s6')">almost there</button>
</section>

<section id="s6">
<p>There are so many things I never say<br>But I hope you feel them</p>
<button onclick="reveal('m4')">tap to reveal</button>
<img src="Ira5.jpg" id="m4" class="photo">
<button onclick="next('quiz')">wait</button>
</section>

<!-- QUIZ -->
<section id="quiz">
<h1>Wait</h1>
<p>Guess your gift</p>
<input type="text" id="guess">
<button onclick="checkGift()">Submit</button>
<p id="quizResult"></p>
</section>

<!-- CHAT -->
<section id="chat">
<div class="chatbox">
<p class="msg left">why are you being like this</p>
<p class="msg right">because you deserve to hear it</p>
<p class="msg left">this is weird</p>
<p class="msg right">maybe</p>
<p class="msg right">but it’s true</p>
</div>
<button onclick="next('end')">continue</button>
</section>

<!-- FINAL -->
<section id="end">
<h1 id="finalText"></h1>

<button onclick="reveal('m5')">tap to reveal</button>
<img src="Ira6.jpg" id="m5" class="photo">

<button onclick="location.reload()">Replay</button>
</section>

</div>

<!-- MUSIC -->
<audio id="music">
<source src="London Thumakda .mp3" type="audio/mpeg">
</audio>

<script>

/* PASSWORD */
function check(){
if(document.getElementById("pass").value==="Gauresh"){
document.getElementById("lock").style.display="none";
document.getElementById("main").style.display="block";
document.getElementById("s1").classList.add("active");

let music=document.getElementById("music");
music.currentTime=47;
music.play();
}else{alert("Wrong password");}
}

/* NAV */
function next(id){
document.querySelectorAll("#main section").forEach(s=>s.classList.remove("active"));
document.getElementById(id).classList.add("active");

if(id==="end"){typeFinal();}
}

/* TYPE START */
let text="Hey Ira";
let i=0;
function typeEffect(){
if(i<text.length){
document.getElementById("typing").innerHTML+=text.charAt(i);
i++;
setTimeout(typeEffect,80);
}}
typeEffect();

/* REVEAL */
function reveal(id){
document.getElementById(id).style.display="block";
}

/* QUIZ */
function checkGift(){
let ans=document.getElementById("guess").value.toLowerCase();

if(ans.includes("bracelet")||ans.includes("handmade")){
document.getElementById("quizResult").innerHTML="how did you know";
setTimeout(()=>{next('chat');},1500);
}else{
document.getElementById("quizResult").innerHTML="nope try again";
}
}

/* FINAL TEXT (WORKING FIXED) */
const finalMessage="If I had to choose again, in every life, I would still choose you.";

function typeFinal(){
let el=document.getElementById("finalText");
el.innerHTML="";
let i=0;

function typing(){
if(i<finalMessage.length){
el.innerHTML+=finalMessage.charAt(i);
i++;
setTimeout(typing,70);
}}
typing();
}

</script>

</body>
</html>
