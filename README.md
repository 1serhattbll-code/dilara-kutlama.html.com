<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Dilara İçin 🌹</title>
<style>
body{
margin:0;
padding:0;
overflow:hidden;
font-family:Arial;
background:#1a1a2e;
color:white;
text-align:center;
}

#stars{
position:fixed;
width:100%;
height:100%;
background:#1a1a2e;
z-index:-2;
}

.star{
position:absolute;
background:white;
border-radius:50%;
width:2px;
height:2px;
animation:twinkle linear infinite;
}

@keyframes twinkle{
0%{opacity:0;}
50%{opacity:1;}
100%{opacity:0;}
}

h1{
margin-top:150px;
font-size:45px;
}

p{
font-size:22px;
width:80%;
margin:auto;
}

button{
margin-top:30px;
padding:15px 30px;
font-size:20px;
border:none;
border-radius:30px;
background:white;
color:#ff4d6d;
cursor:pointer;
}

.heart{
position:absolute;
color:white;
font-size:20px;
animation:fall 5s linear infinite;
}

@keyframes fall{
0%{transform:translateY(-100px) scale(0.5);}
100%{transform:translateY(100vh) scale(1);}
}

.confetti{
position:fixed;
width:10px;
height:10px;
background: #ff4d6d;
top:0;
left:50%;
opacity:0.9;
animation:confettifall linear 3s forwards;
}

@keyframes confettifall{
0%{transform:translateY(0) rotate(0deg);}
100%{transform:translateY(100vh) rotate(360deg);}
}
</style>
</head>

<body>

<div id="stars"></div>

<h1>🌹 Dünya Kadınlar Günün Kutlu Olsun</h1>
<p>
Hayatımda tanıdığım en özel kadınlardan birisin.  
Yanında olamasam da bugün seni düşündüğümü bilmeni istedim.  
İyi ki varsın, <strong>Dilara</strong> ❤️
</p>

<button onclick="surpriz()">Sürpriz için tıkla</button>

<script>
// Yıldız oluştur
for(let i=0;i<100;i++){
    let star=document.createElement("div");
    star.classList.add("star");
    star.style.top=Math.random()*100+"%";
    star.style.left=Math.random()*100+"%";
    star.style.width=Math.random()*3+"px";
    star.style.height=star.style.width;
    star.style.animationDuration=(Math.random()*3+2)+"s";
    document.getElementById("stars").appendChild(star);
}

// Kalpler uçuyor
function createHeart(){
    const heart=document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*100+"vw";
    heart.style.animationDuration=(Math.random()*3+2)+"s";
    document.body.appendChild(heart);
    setTimeout(()=>{heart.remove();},5000);
}
setInterval(createHeart,300);

// Sürpriz buton
function surpriz(){
    alert("Sürpriz: Seni çok seviyorum ❤️");
    for(let i=0;i<50;i++){
        let conf=document.createElement("div");
        conf.classList.add("confetti");
        conf.style.left=Math.random()*100+"vw";
        conf.style.background=["#ff4d6d","#ffeb3b","#4fc3f7","#9c27b0"][Math.floor(Math.random()*4)];
        document.body.appendChild(conf);
        setTimeout(()=>{conf.remove();},3000);
    }
}
</script>

</body>
</html>
