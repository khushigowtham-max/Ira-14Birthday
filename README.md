<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: black;
    color: white;
    text-align: center;
}

/* sections */
section {
    height: 100vh;
    display: none;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
}

/* only first visible */
#s1 {
    display: flex;
}

/* text */
h1 {
    font-size: 3em;
    margin-bottom: 20px;
}

p {
    max-width: 600px;
    font-size: 1.3em;
    line-height: 1.8;
}

/* button */
button {
    margin-top: 30px;
    padding: 15px 30px;
    border-radius: 25px;
    border: none;
    background: white;
    color: black;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}

/* images */
.photo {
    width: 250px;
    border-radius: 15px;
    margin-top: 20px;
}

/* hearts */
.heart {
    position: fixed;
    color: pink;
    animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
}
</style>

</head>

<body>

<!-- SECTION 1 -->
<section id="s1">
    <h1 id="typing"></h1>
    <button onclick="next('s2')">Continue</button>
</section>

<!-- SECTION 2 -->
<section id="s2">
    <p>
        I do not think I say this enough, but you changed my life in a way I never expected.
    </p>
    <button onclick="next('s3')">Continue</button>
</section>

<!-- SECTION 3 -->
<section id="s3">
    <p>
        You became the person I go to without thinking.
        The person I trust without explaining everything.
    </p>
    <img src="photo1.jpg" class="photo">
    <button onclick="next('s4')">Continue</button>
</section>

<!-- SECTION 4 -->
<section id="s4">
    <p>
        It is not just the big memories.
        It is the random conversations that somehow mean the most.
    </p>
    <img src="photo2.jpg" class="photo">
    <button onclick="next('s5')">Continue</button>
</section>

<!-- SECTION 5 -->
<section id="s5">
    <p>
        You are not just my best friend.
        You are someone who stayed, understood, and made life better.
    </p>
    <button onclick="next('s6')">Continue</button>
</section>

<!-- SECTION 6 -->
<section id="s6">
    <p>
        Happy Birthday.
        I hope this year gives you everything you deserve.
    </p>
    <button onclick="next('end')">Last</button>
</section>

<!-- FINAL -->
<section id="end">
    <p>
        If I had to choose again, I would still choose you.
    </p>
</section>

<!-- MUSIC -->
<audio autoplay loop>
    <source src="song.mp3" type="audio/mpeg">
</audio>

<script>
// navigation
function next(id) {
    document.querySelectorAll("section").forEach(s => s.style.display = "none");
    document.getElementById(id).style.display = "flex";
}

// typing effect
const text = "Hey Ira";
let i = 0;

function typeEffect() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 80);
    }
}
typeEffect();

// hearts
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "♥";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 6000);
}
setInterval(createHeart, 400);
</script>

</body>
</html>
