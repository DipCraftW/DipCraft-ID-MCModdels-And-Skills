<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>DipStore</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;

    /* BACKGROUND GAMBAR */
    background: url("https://i.ibb.co/Jjxw5fPK/IMG-20260416-132400.png") no-repeat center center fixed;
    background-size: cover;

    color: white;
    position: relative;
}

/* overlay biar gak silau */
body::before {
    content: "";
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.55);
    z-index: -1;
}

.banner {
    width: 100%;
    height: 220px;
    object-fit: cover;
}

.top-social {
    text-align: center;
    margin: 25px 0;
}

.top-social a {
    display: inline-block;
    margin: 6px;
    padding: 10px 15px;
    background: #2a2a2a;
    color: white;
    text-decoration: none;
    border-radius: 10px;
    transition: 0.3s;
}

.top-social a:hover {
    background: #a64dff;
    transform: translateY(-3px);
}

.products {
    padding: 15px;
}

/* CARD */
.card {
    background: #2a2a2a;
    border-radius: 15px;
    margin: 15px;
    overflow: hidden;
    box-shadow: 0 0 15px rgba(0,0,0,0.6);
    transition: 0.4s;

    opacity: 0;
    transform: translateY(60px) scale(0.95);
    filter: blur(8px);
}

.card.show {
    opacity: 1;
    transform: translateY(0) scale(1);
    filter: blur(0);
}

.card:hover {
    transform: translateY(-5px) scale(1.05);
}

.card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
}

.card-title {
    padding: 12px;
    font-size: 18px;
    font-weight: bold;
    color: white;
    text-align: center;
}

.card-btn {
    display: block;
    margin: 10px auto 15px;
    padding: 10px 20px;
    background: linear-gradient(45deg, #a64dff, #6a00ff);
    color: white;
    text-decoration: none;
    border-radius: 10px;
    font-weight: bold;
    transition: 0.3s;
    text-align: center;
}

.card-btn:hover {
    transform: scale(1.1);
}

footer {
    margin-top: 30px;
    padding: 15px;
    background-color: #1a0033;
    text-align: center;
}
</style>
</head>

<body>

<img src="https://i.imgur.com/Yr3Sr72.jpg" class="banner">

<div class="top-social">
    <a href="https://wa.me/6285737248938">📱 WhatsApp</a>
    <a href="https://www.instagram.com/d11ptaa" target="_blank">📸 Instagram</a>
    <a href="https://www.youtube.com/@DiptaCraft" target="_blank">▶ YouTube</a>
</div>

<div class="products">

<div class="card">
    <img src="https://i.imgur.com/7vp7tVJ.jpeg">
    <div class="card-title">Keris Sakti | Rp 30.000</div>
    <a href="https://wa.me/6285737248938?text=Saya%20mau%20beli%20Keris%20Sakti" class="card-btn" onclick="klikSound()">BUY</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/jN9Yqy5.jpeg">
    <div class="card-title">Pyropex Of Staff | Rp 30.000</div>
    <a href="https://wa.me/6285737248938?text=Saya%20mau%20beli%20Pyropex%20Of%20Staff" class="card-btn" onclick="klikSound()">BUY</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/dyxaZeC.jpeg">
    <div class="card-title">Gladius Primordium</div>
    <a href="https://www.mediafire.com/file/example/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/cRkIHXb.png">
    <div class="card-title">DawnShard Of Light</div>
    <a href="https://www.mediafire.com/file/4rillanczkbycsb/DiptaRPG_DawnshardOfLight.zip/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/TkEa1vo.png">
    <div class="card-title">One Percent Lust</div>
    <a href="https://www.mediafire.com/file/vretg8n05mgyfhk/ONE_PERCENT_SIN_OF_LUST.tar.gz/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/PIYSHJf.png">
    <div class="card-title">The Greatest Sun Of Sword</div>
    <a href="https://www.mediafire.com/file/28f7mu74q63408f/%255BDiptaRPG%255D_The_Greatest_Sun_Of_Sword.tar.gz/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/p4F8GnR.png">
    <div class="card-title">Angel Of Sympathy</div>
    <a href="https://www.mediafire.com/file/x9jftja2tm4w4nc/%255BDipCraftRPG%255D_AngelOf_Sympathy.tar.gz/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

<div class="card">
    <img src="https://i.imgur.com/KjUvzfB.png">
    <div class="card-title">Somnus Aerternam Staff</div>
    <a href="https://www.mediafire.com/file/4dwlf6lewyowyeq/%5BSPRING%5D_Archmage_Evolution_%28Sloth%29.zip/file" class="card-btn" onclick="klikSound()">DOWNLOAD</a>
</div>

</div>

<footer>© DipzStore</footer>

<script>
const cards = document.querySelectorAll('.card');

const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
            setTimeout(() => {
                entry.target.classList.add('show');
            }, i * 120);
        }
    });
}, { threshold: 0.2 });

cards.forEach(card => observer.observe(card));

function klikSound(){
    if (navigator.vibrate) navigator.vibrate(50);
    let audio = new Audio('https://www.soundjay.com/buttons/sounds/button-16.mp3');
    audio.play();
}
</script>

</body>
</html>
