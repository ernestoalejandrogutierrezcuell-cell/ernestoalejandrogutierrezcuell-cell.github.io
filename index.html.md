<!DOCTYPE html>  
<html lang="es">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>Para Melissa ❤️</title>  
  
<style>  
body{  
    margin:0;  
    height:100vh;  
    overflow:hidden;  
    background:black;  
    font-family:Arial, sans-serif;  
    display:flex;  
    justify-content:center;  
    align-items:center;  
    color:white;  
}  
  
/* Pantalla inicial */  
#login{  
    text-align:center;  
    z-index:20;  
}  
  
input{  
    padding:12px;  
    border-radius:10px;  
    border:none;  
    font-size:18px;  
    text-align:center;  
}  
  
button{  
    margin-top:12px;  
    padding:10px 20px;  
    border:none;  
    border-radius:10px;  
    background:#ff4d6d;  
    color:white;  
    font-size:16px;  
    cursor:pointer;  
}  
  
/* Transición cinematográfica */  
.fade{  
    animation: fadeIn 2s forwards;  
}  
  
@keyframes fadeIn{  
    from{opacity:0;}  
    to{opacity:1;}  
}  
  
/* Contenido oculto */  
#contenido{  
    display:none;  
    text-align:center;  
    position:relative;  
    z-index:10;  
}  
  
/* Texto latiendo */  
.cartel{  
    font-size:8vw;  
    font-weight:bold;  
    animation: latido 1s infinite;  
}  
  
@keyframes latido{  
    0%{ transform:scale(1);}  
    50%{ transform:scale(1.1);}  
    100%{ transform:scale(1);}  
}  
  
/* Corazones */  
.corazon{  
    position:absolute;  
    animation: flotar linear infinite;  
}  
  
@keyframes flotar{  
    0%{ transform:translateY(100vh) scale(0.5); opacity:1; }  
    100%{ transform:translateY(-10vh) scale(1.2); opacity:0; }  
}  
  
/* Estrellas */  
.estrella{  
    position:absolute;  
    width:2px;  
    height:2px;  
    background:white;  
    animation: brillar 2s infinite alternate;  
}  
  
@keyframes brillar{  
    from{opacity:0.2;}  
    to{opacity:1;}  
}  
</style>  
</head>  
  
<body>  
  
<div id="login">  
    <h2>Ingresa la contraseña</h2>  
    <input type="password" id="password" placeholder="Contraseña">  
    <br>  
    <button onclick="verificar()">Entrar</button>  
</div>  
  
<div id="contenido">  
    <div class="cartel">TE AMO MELISSA ❤️</div>  
  
    <!-- Música -->  
    <iframe width="0" height="0"  
    src="https://www.youtube.com/embed/bpOSxM0rNPM?autoplay=1&loop=1&playlist=bpOSxM0rNPM"  
    frameborder="0"  
    allow="autoplay">  
    </iframe>  
</div>  
  
<script>  
function verificar(){  
    let pass = document.getElementById("password").value;  
    if(pass === "Te Odio"){  
        document.getElementById("login").style.display="none";  
        document.getElementById("contenido").style.display="block";  
        document.body.classList.add("fade");  
        generarCorazones();  
        generarEstrellas();  
    } else {  
        alert("Contraseña incorrecta");  
    }  
}  
  
function generarCorazones(){  
    setInterval(()=>{  
        let c = document.createElement("div");  
        c.classList.add("corazon");  
        c.innerHTML="❤";  
        c.style.left=Math.random()*100+"vw";  
        c.style.fontSize=(Math.random()*25+15)+"px";  
        c.style.color=`hsl(${Math.random()*360},100%,70%)`;  
        c.style.animationDuration=(Math.random()*3+3)+"s";  
        document.body.appendChild(c);  
        setTimeout(()=>{c.remove();},6000);  
    },300);  
}  
  
function generarEstrellas(){  
    for(let i=0;i<120;i++){  
        let e=document.createElement("div");  
        e.classList.add("estrella");  
        e.style.top=Math.random()*100+"vh";  
        e.style.left=Math.random()*100+"vw";  
        e.style.animationDuration=(Math.random()*2+1)+"s";  
        document.body.appendChild(e);  
    }  
}  
</script>  
  
</body>  
</html>  
