<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mystic Network</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
<script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
<style>
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Roboto',sans-serif;background:#0f0f0f;color:#fff;display:flex;flex-direction:column;min-height:100vh;overflow-x:hidden;position:relative;}




header{text-align:center;padding:80px 20px;background: linear-gradient(135deg, #ff416c, #ff4b2b);clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);}
header h1{font-size:3rem;margin-bottom:10px;text-shadow:2px 2px 5px rgba(0,0,0,0.5);}
header p{font-size:1.2rem;color:#f1f1f1;}
.container{flex:1;max-width:900px;margin:-50px auto 50px auto;padding:0 20px;display:flex;flex-direction:column;align-items:center;text-align:center;}
.btn{display:inline-flex;align-items:center;justify-content:center;margin:15px;padding:18px 40px;font-size:1.2rem;font-weight:700;border:none;border-radius:12px;cursor:pointer;transition:all 0.3s ease;box-shadow:0 5px 15px rgba(0,0,0,0.3);}
.btn i{margin-right:10px;}
.discord-btn{background:#7289da;color:#fff;}
.discord-btn:hover{background:#5b6eae;transform:translateY(-3px);box-shadow:0 8px 20px rgba(114,137,218,0.5);}
.shop-btn{background:linear-gradient(135deg,#ff416c,#ff4b2b);color:#fff;}
.shop-btn:hover{background:linear-gradient(135deg,#ff4b2b,#ff416c);transform:translateY(-3px);box-shadow:0 8px 20px rgba(255,75,43,0.5);}
.copy-btn{background:#1abc9c;color:#fff;}
.copy-btn:hover{background:#16a085;transform:translateY(-3px);box-shadow:0 8px 20px rgba(26,188,156,0.5);}
.staff-btn{background:#ff0000;color:#fff;}
.staff-btn:hover{background:#cc0000;transform:translateY(-3px);box-shadow:0 8px 20px rgba(255,0,0,0.5);}
.info{font-size:1.2rem;margin-top:25px;color:#f1f1f1;min-height:1.5em;}
footer{text-align:center;padding:20px;background:#111;color:#888;font-size:0.9rem;}

/* Modal Staff */
.modal{display:none;position:fixed;z-index:1000;left:0;top:0;width:100%;height:100%;overflow:auto;background-color: rgba(0,0,0,0.9);animation:fadeIn 0.5s;}
.modal-content{background:#1a1a1a;margin:10% auto;padding:30px;border-radius:15px;width:90%;max-width:500px;position:relative;text-align:left;box-shadow:0 8px 30px rgba(0,0,0,0.5);transform:translateY(-100px);opacity:0;animation:slideIn 0.5s forwards;}
.close{color:#fff;position:absolute;top:15px;right:20px;font-size:1.5rem;cursor:pointer;}
.staff-member{margin:12px 0;font-size:1.2rem;font-weight:700;display:flex;align-items:center;animation:neonGlow 2s infinite alternate;}
.staff-member i{margin-right:10px;}
.staff-skin-cube {
  margin-top: 5px;
  width: 60px;
  height: 60px;
  border-radius: 8px;
  overflow: hidden;
  background: #111;
  display: inline-block;
  margin-left: 10px;
  box-shadow: 0 0 15px rgba(255,255,255,0.3);
  animation: floatCube 2s ease-in-out infinite alternate;
}
.staff-skin-cube img { width: 100%; height: 100%; object-fit: cover; }
.staff-skin-cube.placeholder { background: linear-gradient(135deg, #333, #555); animation: placeholderGlow 1.5s infinite alternate, floatCube 2s ease-in-out infinite alternate; }

/* Roles con brillo animado */
.staff-member.owner{ color:#ff0000; animation: glowRed 1.5s infinite alternate; }
.staff-member.manager{ color:#b266ff; animation: glowViolet 1.5s infinite alternate; }
.staff-member.helper{ color:#00fff7; animation: glowAqua 1.5s infinite alternate; }
.staff-member.bughunter{ color:#ff8000; animation: glowOrange 1.5s infinite alternate; }
.staff-member.builder{ color:#ff66aa; animation: glowPink 1.5s infinite alternate; }

/* Animaciones */
@keyframes floatCube{0%{transform:translateY(0px);}50%{transform:translateY(-8px);}100%{transform:translateY(0px);}}
@keyframes placeholderGlow{0%{background:linear-gradient(135deg,#333,#555);}50%{background:linear-gradient(135deg,#444,#666);}100%{background:linear-gradient(135deg,#333,#555);}}
@keyframes glowRed{0%{text-shadow:0 0 5px #ff4c4c,0 0 10px #ff0000;}50%{text-shadow:0 0 10px #ff1a1a,0 0 20px #ff4c4c;}100%{text-shadow:0 0 5px #ff4c4c,0 0 10px #ff0000;}}
@keyframes glowViolet{0%{text-shadow:0 0 5px #b266ff,0 0 10px #8a2be2;}50%{text-shadow:0 0 10px #a64dff,0 0 20px #b266ff;}100%{text-shadow:0 0 5px #b266ff,0 0 10px #8a2be2;}}
@keyframes glowAqua{0%{text-shadow:0 0 5px #00fff7,0 0 10px #00b3b3;}50%{text-shadow:0 0 10px #00e6e6,0 0 20px #00fff7;}100%{text-shadow:0 0 5px #00fff7,0 0 10px #00b3b3;}}
@keyframes glowOrange{0%{text-shadow:0 0 5px #ffbf00,0 0 10px #ff8000;}50%{text-shadow:0 0 10px #ffaa00,0 0 20px #ffbf00;}100%{text-shadow:0 0 5px #ffbf00,0 0 10px #ff8000;}}
@keyframes glowPink{0%{text-shadow:0 0 5px #ff99cc,0 0 10px #ff66aa;}50%{text-shadow:0 0 10px #ff66aa,0 0 20px #ff99cc;}100%{text-shadow:0 0 5px #ff99cc,0 0 10px #ff66aa;}}
@keyframes slideIn{0%{transform:translateY(-100px);opacity:0;}100%{transform:translateY(0);opacity:1;}}
@keyframes fadeIn{0%{opacity:0;}100%{opacity:1;}}
@keyframes neonGlow{0%{text-shadow:0 0 5px #fff,0 0 10px currentColor;}50%{text-shadow:0 0 10px #fff,0 0 20px currentColor;}100%{text-shadow:0 0 5px #fff,0 0 10px currentColor;}}

/* Partículas de fondo */
.particle{position:absolute;width:6px;height:6px;background:white;border-radius:50%;opacity:0.7;animation:moveParticle linear infinite;}
@keyframes moveParticle{0%{transform:translateY(0);}100%{transform:translateY(-100vh);}}
</style>
</head>
<body>

<header>
<h1>Mystic Network</h1>
<p>¡El mejor servidor de Minecraft para disfrutar con amigos!</p>
</header>

<div class="container">
<button class="btn discord-btn" onclick="window.open('https://discord.gg/FFRWd64hap','_blank')"><i class="fab fa-discord"></i> Unirse al Discord</button>
<button class="btn shop-btn" onclick="window.open('https://mystyc-network.tebex.io/','_blank')"><i class="fas fa-shopping-cart"></i> Ir a la Tienda</button>
<button class="btn copy-btn" onclick="copyText('Mc.MysticNetwork.es')"><i class="fas fa-copy"></i> Copiar IP del Servidor</button>
<button class="btn staff-btn" onclick="openModal()"><i class="fas fa-users"></i> Staff</button>
<div class="info" id="copiedMessage"></div>
</div>

<!-- Modal Staff -->
<div id="staffModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal()">&times;</span>
    <h2 style="text-align:center;margin-bottom:20px;">Staff del Servidor</h2>

    <!-- Staff Members -->
    <div class="staff-member owner"><i class="fas fa-crown"></i> Ezequiel1932 (Owner)<div class="staff-skin-cube"><img src="https://es.namemc.com/profile/ezequiel1932.2" alt="Skin de Ezequiel1932"/></div></div>
    <div class="staff-member owner"><i class="fas fa-crown"></i> Gabito (Owner)<div class="staff-skin-cube placeholder"></div></div>
    <div class="staff-member manager"><i class="fas fa-user-shield"></i> Teo (Manager)<div class="staff-skin-cube placeholder"></div></div>
    <div class="staff-member helper"><i class="fas fa-hands-helping"></i> Gokicha-San (Helper)<div class="staff-skin-cube"><img src="https://es.namemc.com/skin/1ac5b0d6d8210ae6" alt="Skin de Gokicha-San"/></div></div>
    <div class="staff-member helper"><i class="fas fa-hands-helping"></i> katzumi (Helper)<div class="staff-skin-cube"><img src="https://mineskin.org/skins/20e2d84520b8475a9e533228defbfe90" alt="Skin de katzumi"/></div></div>
    <div class="staff-member helper"><i class="fas fa-hands-helping"></i> Moriuske (Helper)<div class="staff-skin-cube placeholder"></div></div>
    <div class="staff-member helper"><i class="fas fa-hands-helping"></i> TomatexZ (Helper)<div class="staff-skin-cube"><img src="https://es.namemc.com/profile/TomatexZ.1" alt="Skin de TomatexZ"/></div></div>
    <div class="staff-member helper"><i class="fas fa-hands-helping"></i> DONOBAN6622 (Helper)<div class="staff-skin-cube"><img src="https://es.namemc.com/profile/Renegado_62.1" alt="Skin de DONOBAN6622"/></div></div>
    <div class="staff-member bughunter"><i class="fas fa-bug"></i> SrBerserker (Bug Hunter)<div class="staff-skin-cube"><img src="https://es.namemc.com/profile/SrBerserker.1" alt="Skin de SrBerserker"/></div></div>
    <div class="staff-member builder"><i class="fas fa-hammer"></i> Duk (Builder)<div class="staff-skin-cube placeholder"></div></div>

  </div>
</div>

<footer>&copy; 2025 Mystic Network. Todos los derechos reservados.</footer>

<script>
// Copiar al portapapeles
function copyText(text){
navigator.clipboard.writeText(text).then(()=>{
document.getElementById('copiedMessage').textContent='¡Texto copiado al portapapeles!';
setTimeout(()=>{document.getElementById('copiedMessage').textContent='';},3000);
}).catch(err=>console.error('Error al copiar: ',err));
}

// Modal
const modal=document.getElementById('staffModal');
function openModal(){ modal.style.display='block'; }
function closeModal(){ modal.style.display='none'; }
window.onclick=function(event){if(event.target==modal){modal.style.display='none';}}

// Partículas de fondo
for(let i=0;i<50;i++){
    let particle=document.createElement('div');
    particle.classList.add('particle');
    particle.style.left=Math.random()*100+'vw';
    particle.style.top=Math.random()*100+'vh';
    particle.style.width=Math.random()*4+2+'px';
    particle.style.height=particle.style.width;
    particle.style.backgroundColor='rgba(255,255,255,'+Math.random()+')';
    particle.style.animationDuration=(Math.random()*10+5)+'s';
    document.body.appendChild(particle);
}
</script>
</body>
</html>
