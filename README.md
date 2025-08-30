<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cuboria — Офіційний сайт</title>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
<style>
:root {--bg:#0f1724;--card:#0b1220;--accent:#6ee7b7;--accent-hover:#3dd5c7;--muted:#9aa7b2;--radius:16px;}
body{margin:0;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Press Start 2P", monospace;color:#e6eef2;background:var(--bg);overflow-x:hidden;transition:0.3s;}
.container{max-width:1200px;margin:0 auto;padding:24px;}
header{display:flex;align-items:center;gap:18px;margin-bottom:32px;flex-wrap:wrap;}
.logo{width:72px;height:72px;background:linear-gradient(135deg,var(--accent),var(--accent-hover));border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:14px;color:#042027;}
nav{margin-left:auto;display:flex;gap:12px;flex-wrap:wrap;}
nav a{color:var(--muted);text-decoration:none;padding:8px 12px;border-radius:10px;font-weight:600;font-size:13px;transition:0.3s;}
nav a:hover{color:var(--accent);background:rgba(255,255,255,0.03);}
.card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:var(--radius);padding:24px;box-shadow:0 8px 30px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03);transition:0.3s;}
.card:hover{transform: translateY(-6px) scale(1.02);box-shadow:0 15px 45px rgba(0,255,255,0.25);}
.title{font-family:"Press Start 2P";font-size:28px;margin:0 0 12px 0;color:var(--accent);}
.version-selector{display:flex;gap:12px;flex-wrap:wrap;margin-top:12px;}
.version-btn{padding:10px 16px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);background:var(--card);color:#e6eef2;cursor:pointer;transition:0.3s;font-weight:600;}
.version-btn:hover{transform: translateY(-3px) scale(1.05);box-shadow:0 8px 25px rgba(0,255,255,0.3);background:linear-gradient(90deg,var(--accent-hover),var(--accent));}
.version-btn.active{transform: scale(1.05);background:linear-gradient(90deg,var(--accent),var(--accent-hover));color:#042027;box-shadow:0 10px 30px rgba(0,255,255,0.5);}
.grid-2{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-bottom:24px;}
@media(max-width:880px){.grid-2{grid-template-columns:1fr;}}
.screens{display:flex;gap:12px;flex-wrap:wrap;}
.screen{width:140px;height:90px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));display:flex;align-items:center;justify-content:center;color:var(--muted);font-size:12px;border:1px dashed rgba(255,255,255,0.02);transition: transform 0.4s, box-shadow 0.4s, filter 0.4s; cursor:pointer;}
.screen:hover{transform: scale(1.1) rotateX(2deg) rotateY(2deg);box-shadow:0 15px 40px rgba(0,255,255,0.3);filter:brightness(1.2);}
footer{margin-top:32px;color:var(--muted);display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;font-size:12px;}
.chip{display:inline-block;padding:6px 12px;border-radius:999px;background:rgba(255,255,255,0.02);color:var(--muted);font-size:13px;}
</style>
</head>
<body>
<div class="container">
<header>
  <div class="logo">CUBO</div>
  <nav>
    <a href="#download">Завантажити</a>
    <a href="#news">Новини</a>
    <a href="#contacts">Контакти</a>
  </nav>
</header>

<section class="card" id="download">
  <h3 class="title">Завантажити гру</h3>
  <div class="version-selector">
    <button class="version-btn active" data-file="Build86.zip">Build 86</button>
    <button class="version-btn" data-file="Build286.zip">Build 286</button>
    <button class="version-btn" data-file="Build365.zip">Build 365</button>
    <button class="version-btn" data-file="Build704.zip">Build 704 (Незабаром...)</button>
  </div>
</section>

<section class="grid-2">
  <div class="card" id="news">
    <h3 class="title">Новини</h3>
    <p>Реліз Build 365 — Нова версія з покращеною графікою та стабільністю.</p>
  </div>
  <div class="card">
    <h3 class="title">Скріншоти</h3>
    <div class="screens">
      <div class="screen">Головний екран</div>
      <div class="screen">Менеджер версій</div>
      <div class="screen">Налаштування</div>
      <div class="screen">Підключення до сервера</div>
    </div>
  </div>
</section>

<section id="contacts" class="card">
  <h3 class="title">Контакти</h3>
  <p>Discord: Приєднатися</p>
  <p>Пошта: melnikandriy57@gmail.com</p>
</section>

<footer>
  <div class="chip">© 2025 Cuboria</div>
  <div class="chip">Версія лаунчера 1.0.0</div>
</footer>

<script>
const versionBtns = document.querySelectorAll('.version-btn');

versionBtns.forEach(btn=>{
  btn.addEventListener('click', ()=>{
    versionBtns.forEach(b=>b.classList.remove('active'));
    btn.classList.add('active');

    const file = btn.dataset.file;
    const a = document.createElement('a');
    a.href = file;
    a.download = file;
    document.body.appendChild(a);
    a.click();
    a.remove();
  });
});
</script>

</body>
</html>
