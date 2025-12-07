# my-website
<!doctype html>
<html lang="uk">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>One-Page Site — Shcherbinina</title>

<style>
/* ——————— ГОЛОВНІ ЗМІННІ ——————— */
:root{
  --bg:#0b0b0d;
  --card:#111115;
  --text:#e6e6e9;
  --muted:#a0a0a6;
  --accent:#ff4da6;
  --mono:"Segoe UI",sans-serif;
}

/* —————— ОСНОВНИЙ СТИЛЬ —————— */
body{
  margin:0;
  padding:20px;
  font-family:var(--mono);
  background:var(--bg);
  color:var(--text);
  display:flex;
  justify-content:center;
}

.container{
  width:100%;
  max-width:1000px;
}

/* BANER */
.banner{
  width:100%;
  height:250px;
  border-radius:12px;
  overflow:hidden;
  margin-bottom:22px;
  animation:fade 1.2s ease;
}
.banner img{
  width:100%;
  height:100%;
  object-fit:cover;
  filter:brightness(0.65);
  transition:0.6s;
}
.banner img:hover{
  filter:brightness(0.88);
  transform:scale(1.03);
}

/* CARD */
.card{
  background:var(--card);
  padding:24px;
  border-radius:12px;
  margin-bottom:22px;
  animation:fadeUp 0.8s ease;
}
.section-title{
  font-size:22px;
  color:var(--accent);
  margin-bottom:14px;
}
a{
  color:var(--accent);
  font-weight:600;
  text-decoration:none;
}
a:hover{opacity:.8}

/* BUTTONS */
.nav-btns{
  display:flex;
  gap:12px;
  margin-bottom:12px;
}
button{
  background:var(--accent);
  color:#fff;
  border:none;
  padding:10px 18px;
  border-radius:7px;
  cursor:pointer;
  font-size:15px;
  font-weight:600;
  transition:0.3s;
}
button:hover{opacity:0.85;transform:translateY(-2px);}

/* HIDING SECTIONS */
.section{display:none;}
.section.active{display:block;}

/* ANIMATIONS */
@keyframes fadeUp{
  from{opacity:0;transform:translateY(20px);}
  to{opacity:1;transform:translateY(0);}
}
@keyframes fade{
  from{opacity:0;}
  to{opacity:1;}
}
</style>

</head>
<body>

<div class="container">

<!-- ======= BANER ======= -->
<div class="banner">
  <img src="banner.jpg" alt="banner">
</div>

<!-- ======= НАВІГАЦІЯ ======= -->
<div class="nav-btns">
  <button onclick="show('resume')">Резюме</button>
  <button onclick="show('econ')">Економічна безпека США</button>
  <button onclick="show('threats')">Загрози та протидія</button>
  <button onclick="show('home')">Головна</button>
</div>

<!-- ======= ГОЛОВНА ======= -->
<div id="home" class="section active">
  <div class="card">
    <h2>Ласкаво просимо!</h2>
    <p>Це односторінковий сайт із 3 навчальними розділами.</p>
    <p>Використовуйте кнопки зверху, щоб перемикатися між сторінками.</p>
  </div>
</div>

<!-- ======= РЕЗЮМЕ ======= -->
<div id="resume" class="section">
  <div class="card">
    <h2 class="section-title">Резюме — Anastasiia Shcherbinina</h2>

    <p><b>Email:</b> <a href="mailto:anasttn@icloud.com">anasttn@icloud.com</a></p>
    <p><b>Телефон:</b> +380 676522107</p>

    <h3 class="section-title">Освіта</h3>
    <p>Complete Secondary Education — Lyceum Hora (Certificate with Distinction).</p>

    <h3 class="section-title">Досвід</h3>
    <p><b>Waitress — Green Villa</b><br>Обслуговування клієнтів, бариста-робота, каса.</p>

    <h3 class="section-title">Навички</h3>
    <ul>
      <li>Командна робота, лідерство</li>
      <li>Barista-навички</li>
      <li>Документообіг, робота під тиском</li>
      <li>Українська, англійська B2, німецька B1, російська</li>
    </ul>

    <h3 class="section-title">Досягнення</h3>
    <ul>
      <li>Certificate with Distinction</li>
      <li>Участь у фестивалях</li>
    </ul>

    <p>PDF резюме: <a href="resume.pdf">resume.pdf</a></p>
  </div>
</div>

<!-- ======= ЕКОНОМІЧНА БЕЗПЕКА ======= -->
<div id="econ" class="section">
  <div class="card">
    <h2 class="section-title">Економічна безпека США</h2>

    <p>Економіка США у 2025 році зростає на рівні 3–3.8%.</p>
    <p>Інфляція стабілізувалась близько 3%.</p>
    <p>Національний борг перевищує $38 трлн.</p>
    <p>FDI сильні, але глобальні інвестиції слабшають.</p>
    <p>Головні виклики — бюджетні дефіцити, геополітика та технологічні ризики.</p>
  </div>
</div>

<!-- ======= ЗАГРОЗИ ======= -->
<div id="threats" class="section">
  <div class="card">
    <h2 class="section-title">Загрози</h2>
    <ol>
      <li>Геополітична напруга та торгові конфлікти</li>
      <li>Зростання державного боргу</li>
      <li>Корупція та слабке регулювання</li>
      <li>Енергетична вразливість</li>
      <li>Технологічні шоки</li>
    </ol>

    <h2 class="section-title">Методи протидії</h2>
    <ol>
      <li>Диверсифікація ринків</li>
      <li>Фіскальна стабілізація</li>
      <li>Антикорупційні реформи</li>
      <li>Інвестиції в енергетику</li>
      <li>Підтримка освіти та інновацій</li>
    </ol>
  </div>
</div>

</div>

<script>
function show(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}
</script>

</body>
</html>
