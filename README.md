<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>DINONESIA HARVEST CITY</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * { margin:0; padding:0; box-sizing:border-box; font-family:'Segoe UI',sans-serif; }
    body { background:#f0f0f0; color:#333; transition:background 0.3s,color 0.3s; scroll-behavior:smooth; }
    header {
      background:linear-gradient(90deg, #0047ab, #0077ff);
      color:#fff; padding:1em 2em;
      display:flex; align-items:center; flex-wrap:wrap; position:sticky; top:0; z-index:1000;
      box-shadow:0 2px 10px rgba(0,0,0,0.2);
    }
    .logo { width:120px; margin-right:1em; } 
    header h2 { flex:1; font-size:1.8em; }
    nav { display:flex; gap:1em; flex-wrap:wrap; }
    nav button {
      background:rgba(255,255,255,0.2); border:none; color:#fff;
      padding:0.6em 1em; border-radius:25px; cursor:pointer;
      transition:all 0.3s; display:flex; align-items:center; gap:0.5em;
    }
    nav button:hover { background:#ff5722; transform:scale(1.05); }
    nav button i { font-size:1.2em; }

    .dark-mode { background:#1e1e1e; color:#ddd; }
    .dark-mode header { background:#002f6c; }
    .dark-mode nav button { color:#ddd; }
    .dark-mode .card { background:#2c2c2c; color:#ddd; }
    .dark-mode footer { background:#002f6c; }

    .dark-toggle {
      background:#ff5722; border:none; color:#fff;
      padding:0.5em 1em; border-radius:25px; cursor:pointer;
      transition:all 0.3s;
    }
    .dark-toggle:hover { background:#e64a19; }

    .container { padding:2em; max-width:1200px; margin:0 auto; }

    .slider { position:relative; overflow:hidden; border-radius:10px; margin-bottom:2em; }
    .slides { display:flex; transition:transform 0.6s ease; }
    .slides img { width:100%; flex-shrink:0; height:400px; object-fit:cover; }
    .slider .prev, .slider .next {
      position:absolute; top:50%; transform:translateY(-50%);
      background:rgba(0,0,0,0.5); color:#fff; border:none; padding:0.6em;
      cursor:pointer; border-radius:50%; z-index:1;
    }
    .prev { left:10px } .next { right:10px }
    .slider .dots {
      position:absolute; bottom:10px; left:50%; transform:translateX(-50%);
      display:flex; gap:5px;
    }
    .slider .dot {
      width:12px; height:12px; background:rgba(255,255,255,0.5);
      border-radius:50%; cursor:pointer;
    }
    .slider .dot.active { background:#ff5722; }

    h3 { margin-bottom:0.5em; color:#0047ab; font-size:1.5em; }
    .section p { margin-bottom:1em; line-height:1.6; font-size:1.1em; }

    .cards { display:grid; grid-template-columns:repeat(auto-fill,minmax(280px,1fr)); gap:1.5em; }
    .card {
      background:#fff; border-radius:12px; overflow:hidden;
      box-shadow:0 4px 12px rgba(0,0,0,0.1); transition:transform 0.4s, opacity 0.4s;
      animation:fadeInUp 0.6s ease forwards;
      opacity:0;
    }
    .card:hover { transform:translateY(-8px); }
    .card img { width:100%; height:160px; object-fit:cover; }
    .card-content { padding:1em; }
    .card-content h4 { margin-bottom:0.5em; color:#0047ab; font-size:1.2em; }

    footer {
      text-align:center; padding:1em;
      background:#0047ab; color:#fff; margin-top:2em;
      box-shadow:0 -2px 8px rgba(0,0,0,0.2);
    }

    .scroll-top {
      position:fixed; bottom:20px; right:20px;
      background:#0047ab; color:#fff; border:none;
      padding:0.7em 1em; border-radius:50%;
      font-size:1.2em; cursor:pointer;
      display:none; z-index:999;
      transition:background 0.3s;
    }
    .scroll-top:hover { background:#002f6c; }

    @keyframes fadeInUp {
      from { transform:translateY(20px); opacity:0; }
      to { transform:translateY(0); opacity:1; }
    }

    @media(max-width:600px){
      nav { width:100%; overflow-x:auto; }
      header h2 { flex:100%; text-align:center; margin:0.5em 0; }
    }
  </style>
</head>
<body>
  <audio id="clickSound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_191c08e103.mp3"></audio>

  <button class="scroll-top" id="scrollTopBtn" onclick="window.scrollTo({top:0, behavior:'smooth'})">
    <i class="fas fa-arrow-up"></i>
  </button>

  <!-- HEADER -->
  <header>
    <img src="https://i.imgur.com/QntCNNu.png" alt="Logo" class="logo">
    <h2>DINONESIA HARVEST CITY</h2>
    <nav>
      <button onclick="playSound(); show('beranda')"><i class="fas fa-home"></i> Beranda</button>
      <button onclick="playSound(); show('wahana')"><i class="fas fa-cogs"></i> Wahana</button>
      <button onclick="playSound(); show('permainan')"><i class="fas fa-gamepad"></i> Permainan</button>
      <button onclick="playSound(); show('tentang')"><i class="fas fa-info-circle"></i> Tentang</button>
      <button onclick="playSound(); show('kontak')"><i class="fas fa-phone-alt"></i> Kontak</button>
    </nav>
    <button class="dark-toggle" id="darkBtn">
      <i class="fas fa-moon"></i> Mode Gelap
    </button>
  </header>

  <!-- KONTEN UTAMA -->
  <div class="container">
    <div id="beranda" class="content active section">
      <div class="slider">
        <div class="slides">
          <img src="https://i.imgur.com/8pAThVW.jpg" alt="Slide 1">
          <img src="https://i.imgur.com/omkxG5w.jpg" alt="Slide 2">
          <img src="https://i.imgur.com/4EBuHsz.jpg" alt="Slide 3">
          <img src="https://i.imgur.com/JHnmnSk.jpg" alt="Slide 4">
        </div>
        <button class="prev" onclick="playSound(); moveSlide(-1)">❮</button>
        <button class="next" onclick="playSound(); moveSlide(1)">❯</button>
        <div class="dots"></div>
      </div>
      <p>Jelajahi petualangan prasejarah di <strong>DINONESIA HARVEST CITY</strong>! Nikmati wahana dinosaurus interaktif, carousel warna-warni, dan karnaval penuh keseruan untuk semua usia.</p>
    </div>

    <div id="wahana" class="content section" style="display:none">
      <h3><i class="fas fa-dinosaur"></i> Wahana</h3>
      <div class="cards" id="wahanaCards"></div>
    </div>

    <div id="permainan" class="content section" style="display:none">
      <h3><i class="fas fa-dice"></i> Permainan Karnaval</h3>
      <div class="cards" id="permainanCards"></div>
    </div>

    <div id="tentang" class="content section" style="display:none">
      <h3><i class="fas fa-info-circle"></i> Tentang Dinonesia</h3>
      <p><strong>Dinonesia Harvest City</strong> adalah taman hiburan edukatif bertema dinosaurus pertama di kota ini. Dengan menggabungkan unsur permainan, wahana, dan pengetahuan, Dinonesia hadir untuk semua usia.</p>
    </div>

    <div id="kontak" class="content section" style="display:none">
      <h3><i class="fas fa-phone-alt"></i> Kontak</h3>
      <p>Hubungi kami melalui:</p>
      <ul>
        <li><strong>Email:</strong> info@dinonesia.id</li>
        <li><strong>Telepon:</strong> +62 812-3456-7890</li>
        <li><strong>Alamat:</strong> Jl. Dino Raya No. 1, Harvest City</li>
      </ul>
    </div>
  </div>

  <footer>
    <p>©2025 DINONESIA HARVEST CITY — All rights reserved.</p>
  </footer>

  <!-- SCRIPT -->
  <script>
    function playSound() {
      const audio = document.getElementById('clickSound');
      audio.currentTime = 0;
      audio.play();
    }

    function show(id) {
      document.querySelectorAll('.content').forEach(c => c.style.display = 'none');
      document.getElementById(id).style.display = 'block';
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // Dark Mode Persistent
    const darkBtn = document.getElementById('darkBtn');
    if (localStorage.getItem('darkMode') === 'true') {
      document.body.classList.add('dark-mode');
    }
    darkBtn.onclick = () => {
      playSound();
      document.body.classList.toggle('dark-mode');
      localStorage.setItem('darkMode', document.body.classList.contains('dark-mode'));
    };

    // Scroll to top button
    const scrollTopBtn = document.getElementById('scrollTopBtn');
    window.onscroll = () => {
      scrollTopBtn.style.display = window.scrollY > 400 ? 'block' : 'none';
    };

    // Slider
    let idx = 0;
    const slides = document.querySelectorAll('.slides img');
    const dotsContainer = document.querySelector('.dots');

    slides.forEach((_, i) => {
      const dot = document.createElement('div');
      dot.classList.add('dot');
      dot.onclick = () => { idx = i; update(); };
      dotsContainer.appendChild(dot);
    });

    function update() {
      document.querySelector('.slides').style.transform = `translateX(-${idx * 100}%)`;
      document.querySelectorAll('.dot').forEach((d, i) => d.classList.toggle('active', i === idx));
    }

    function moveSlide(n) {
      idx = (idx + n + slides.length) % slides.length;
      update();
    }

    update();
    setInterval(() => { idx = (idx + 1) % slides.length; update(); }, 5000);

    // Render Cards
    const wahanaData = [
      ['Merry Go Round', 'https://i.imgur.com/cARkW0v.jpg', 'fa-horse'],
      ['Dino Swing', 'https://i.imgur.com/FUJFa0M.jpg', 'fa-fan'],
      ['Speed Racing', 'https://i.imgur.com/oZUvCj6.jpg', 'fa-flag-checkered'],
      ['Dino Ride', 'https://i.imgur.com/bnTy8G2.jpg', 'fa-kiwi-bird'],
      ['Sky Race', 'https://i.imgur.com/jlDGJmH.jpg', 'fa-rocket'],
      ['Cano River', 'https://i.imgur.com/xm4dxNs.jpg', 'fa-water'],
      ['Dino Hopper', 'https://i.imgur.com/qmdhNKc.jpg', 'fa-frog'],
      ['Magic Bike', 'https://i.imgur.com/sZTwW9x.jpg', 'fa-bicycle'],
      ['Choochoo Train', 'https://i.imgur.com/qIzDjvT.jpg', 'fa-train'],
      ['Batrey Bike', 'https://i.imgur.com/B2WVG8u.jpg', 'fa-battery-full'],
      ['Ferris Wheel', 'https://i.imgur.com/gISJhjq.jpg', 'fa-circle']
    ];
    const permainanData = [
      ['Fun Bowling', 'https://i.imgur.com/VwllUsY.jpg', 'fa-bowling-ball'],
      ['Jungle Hunting', 'https://i.imgur.com/4KexCl9.jpg', 'fa-crosshairs'],
      ['Crazy Teeth', 'https://i.imgur.com/fW1GJZo.jpg', 'fa-tooth'],
      ['Crazy Bottle', 'https://i.imgur.com/oDKQe1F.jpg', 'fa-wine-bottle'],
      ['Smash Can', 'https://i.imgur.com/S9EZB8m.jpg', 'fa-trash-alt'],
      ['Smash the Clown', 'https://i.imgur.com/WzOQoZ5.jpg', 'fa-theater-masks'],
      ['Duck Ring Toss', 'https://i.imgur.com/KG4HNLl.jpg', 'fa-ring']
    ];

    function renderCards(data, containerId) {
      const container = document.getElementById(containerId);
      container.innerHTML = '';
      data.forEach(([title, img, icon], i) => {
        const delay = i * 0.1;
        container.innerHTML += `
          <div class="card" style="animation-delay:${delay}s">
            <img src="${img}" alt="${title}">
            <div class="card-content">
              <h4><i class="fas ${icon}"></i> ${title}</h4>
            </div>
          </div>`;
      });
    }

    renderCards(wahanaData, 'wahanaCards');
    renderCards(permainanData, 'permainanCards');
  </script>
</body>
</html>
