```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Amit ❤️ Sona</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: "Poppins", sans-serif;
}

body{
    min-height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff4f81,#ff1493,#ff69b4,#ff007f);
    background-size:400% 400%;
    animation:bg 10s ease infinite;
    color:white;
}

@keyframes bg{
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}

/* Glow circles */
body::before,
body::after{
    content:"";
    position:absolute;
    width:350px;
    height:350px;
    border-radius:50%;
    background:rgba(255,255,255,.12);
    filter:blur(5px);
    animation:float 6s infinite alternate;
}

body::before{
    top:-100px;
    left:-100px;
}

body::after{
    bottom:-100px;
    right:-100px;
    animation-delay:2s;
}

@keyframes float{
    from{transform:translate(0,0) scale(1)}
    to{transform:translate(80px,50px) scale(1.3)}
}

.card{
    position:relative;
    z-index:5;
    width:90%;
    max-width:650px;
    padding:45px 30px;
    text-align:center;
    border-radius:30px;
    background:rgba(255,255,255,.15);
    border:1px solid rgba(255,255,255,.35);
    box-shadow:0 20px 60px rgba(120,0,60,.4);
    backdrop-filter:blur(15px);
    animation:cardIn 1.5s ease;
}

@keyframes cardIn{
    from{
        opacity:0;
        transform:scale(.7) translateY(50px);
    }
    to{
        opacity:1;
        transform:scale(1) translateY(0);
    }
}

.heart{
    font-size:75px;
    animation:heartbeat 1.2s infinite;
    text-shadow:0 0 25px #fff;
}

@keyframes heartbeat{
    0%,100%{transform:scale(1)}
    50%{transform:scale(1.25)}
}

h1{
    font-size:48px;
    margin:15px 0;
    text-shadow:0 0 20px #fff;
}

.name{
    color:#fff;
    font-weight:bold;
}

.love{
    color:#ffd1e6;
}

.message{
    font-size:19px;
    line-height:1.7;
    margin:20px 0;
}

button{
    border:none;
    padding:14px 30px;
    border-radius:50px;
    background:white;
    color:#ff1493;
    font-size:17px;
    font-weight:bold;
    cursor:pointer;
    box-shadow:0 0 25px rgba(255,255,255,.7);
    transition:.3s;
}

button:hover{
    transform:scale(1.1);
    box-shadow:0 0 40px white;
}

#secret{
    display:none;
    margin-top:25px;
    font-size:20px;
    animation:fade 1s ease;
}

@keyframes fade{
    from{opacity:0; transform:translateY(20px)}
    to{opacity:1; transform:translateY(0)}
}

/* Floating hearts */
.floating-heart{
    position:absolute;
    bottom:-50px;
    font-size:25px;
    animation:rise linear forwards;
    opacity:.8;
}

@keyframes rise{
    0%{
        transform:translateY(0) rotate(0deg);
        opacity:0;
    }
    10%{opacity:1}
    100%{
        transform:translateY(-110vh) rotate(360deg);
        opacity:0;
    }
}

.footer{
    margin-top:25px;
    font-size:14px;
    opacity:.8;
}
</style>
</head>

<body>

<div class="card">

    <div class="heart">❤️</div>

    <h1>
        <span class="name">Amit</span>
        <span class="love">❤️</span>
        <span class="name">Sona</span>
    </h1>

    <p class="message">
        Some love stories are written in books,
        but the most beautiful ones are written
        in two hearts. 💕
        <br><br>
        <b>Amit & Sona</b> — together, forever and always. 💖
    </p>

    <button onclick="showLove()">
        💌 Open My Heart
    </button>

    <div id="secret">
        "Sona, you are not just a part of my life...
        <br>
        You are the most beautiful part of it." ❤️
        <br><br>
        Forever Yours — <b>Amit 💕</b>
    </div>

    <div class="footer">
        Made with ❤️ specially for Amit & Sona
    </div>

</div>

<script>

function showLove(){
    document.getElementById("secret").style.display="block";
}

/* Create floating hearts */
function createHeart(){

    const heart=document.createElement("div");

    heart.className="floating-heart";

    const hearts=["❤️","💕","💗","💖","💘","💝","🌸"];

    heart.innerHTML=hearts[
        Math.floor(Math.random()*hearts.length)
    ];

    heart.style.left=Math.random()*100+"vw";

    heart.style.animationDuration=
        (4+Math.random()*5)+"s";

    heart.style.fontSize=
        (18+Math.random()*25)+"px";

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },9000);
}

setInterval(createHeart,350);

</script>

</body>
</html>
```
