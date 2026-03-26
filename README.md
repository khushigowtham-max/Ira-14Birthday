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
    opacity: 0;
    transition: opacity 1s;
}

section.active {
    display: flex;
    opacity: 1;
}

#lock {
    display: flex;
    opacity: 1;
}

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
    margin-top: 25px;
    padding: 12px 25px;
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
    display: none;
}

/* video */
video {
    width: 300px;
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
    #lock h1, #lock p, #lock input, #lock button {
    animation: fadeIn 2s ease;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
    <h1>Enter something only we know</h1>
    <input type="password" id="pass">
    <p style="margin-top:10px; opacity:0.7;">
        Hint: Who is better for Akanksha over Yogesh???
    </p>
    <button onclick="check()">Enter</button>
</section>

<!-- MAIN -->
<div id="main">

<section id="s1">
    <h1 id="typing"></h1>
    <button onclick="next('s2')">Continue</button>
</section>

<section id="s2">
    <p>
        I do not think I say this enough, but you changed my life in a way I never expected.
    </p>

    <button onclick="reveal('m1')">Tap to reveal memory</button>
    <img src="Ira3.jpg" id="m1" class="photo">

    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3">
    <p>
        You became the person I go to without thinking.
        The person I trust without explaining everything.
    </p>

    <button onclick="reveal('m2')">Tap to reveal memory</button>
    <img src="Ira1.jpg" id="m2" class="photo">

    <button onclick="next('s4')">Continue</button>
</section>

<section id="s4">
    <p>
        These moments meant more than I ever said.
    </p>

    <video controls>
        <source src="Ira Video.mp4" type="video/mp4">
    </video>

    <button onclick="next('s5')">Continue</button>
</section>

<section id="s5">
    <p>
        It is not just the big memories.
        It is the random moments that somehow became everything.
    </p>

    <button onclick="reveal('m3')">Tap to reveal memory</button>
    <img src="Ira2.jpg" id="m3" class="photo">

    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6">
    <p>
        You are not just my best friend.
        You are someone who stayed and made life better.
    </p>

    <button onclick="reveal('m4')">Tap to reveal</button>
    <img src="Ira5.jpg" id="m4" class="photo">

    <button onclick="next('end')">Last</button>
</section>

<section id="end">
    <p>
        If I had to choose again, I would still choose you.
    </p>

    <button onclick="reveal('m5')">Tap to reveal</button>
    <img src="Ira6.jpg" id="m5" class="photo">
</section>

</div>

<!-- MUSIC -->
<audio id="music">
    <source src="London Thumakda .mp3" type="audio/mpeg">
</audio>

<script>

<section id="lock" class="active" style="position:relative; overflow:hidden;">

    <!-- background image -->
    <img src="bg2.jpg" style="
        position:absolute;
        width:100%;
        height:100%;
        object-fit:cover;
        opacity:0.3;
        z-index:-1;
    ">

    <h1 style="font-size:2.5em;">
        This is not just a website
    </h1>

    <p style="opacity:0.8; margin-bottom:20px;">
        It is something I made for you
    </p>

    <input type="password" id="pass" placeholder="Enter something only we know">

    <p style="margin-top:10px; opacity:0.7;">
        Hint: Who is better for Akanksha over Yogesh
    </p>

    <button onclick="check()">Enter</button>

</section>

</body>
</html>
