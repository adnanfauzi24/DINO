<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>DINONESIA HARVEST CITY</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap" rel="stylesheet">
  <style>
    * { margin:0; padding:0; box-sizing:border-box; font-family:'Segoe UI',sans-serif; }
    body {
      background: linear-gradient(to bottom, #b2ebf2, #ffffff, #fff8e1);
      color:#333; transition:background 0.3s,color 0.3s; scroll-behavior:smooth;
    }
    .color-switcher {
      display: flex; gap: 0.5em; margin: 1em;
    }
    .color-btn {
      border: none; padding: 0.5em 1em; border-radius: 20px; cursor: pointer;
      font-weight: bold; transition: background 0.3s;
    }
    .color1 { background: #b2ebf2; }
    .color2 { background: #ffe082; }
    .color3 { background: #d1c4e9; }
    .color4 { background: #c8e6c9; }
    .color5 { background: #ffccbc; }

    header {
      background:linear-gradient(90deg, #0047ab, #00bcd4); color:#fff;
      padding:1em 2em; display:flex; align-items:center; flex-wrap:wrap;
      position:sticky; top:0; z-index:1000; box-shadow:0 2px 10px rgba(0,0,0,0.3);
      width:100%; max-width:1200px; margin:0 auto;
    }
    .logo {
      width: 200px;
      margin: 0 auto 0.5em;
      display: block;
    }
    header h2 {
      font-size: 2em;
      color: #ffe082;
      text-shadow: 1px 1px 2px #000;
      font-family: 'Fredoka One', cursive;
      text-align: center;
    }
    .a4-slide {
      width: 21cm;
      height: 29.7cm;
      margin: 1cm auto;
      background: #fff;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      padding: 1cm;
      box-sizing: border-box;
      page-break-after: always;
    }
    nav { display:flex; gap:1em; flex-wrap:wrap; }
    nav button {
      background:linear-gradient(to right, #ff9800, #ff5722);
      border:none; color:#fff;
      padding:0.6em 1em; border-radius:25px; cursor:pointer; transition:all 0.3s;
      display:flex; align-items:center; gap:0.5em; font-weight:bold;
    }
    nav button:hover, nav button.active {
      background:#ff3d00; transform:scale(1.1);
    }
    nav button i { font-size:1.2em; animation:bounce 1.5s infinite; }
    .dark-mode {
      background: linear-gradient(to bottom, #1e1e1e, #121212);
      color:#ddd;
    }
    .dark-mode header { background:#263238; }
    .dark-mode nav button { color:#fff; background:#455a64; }
    .dark-mode .card { background:#2c2c2c; color:#ddd; }
    .dark-mode footer { background:#263238; }
    .dark-toggle {
      background:linear-gradient(to right, #ff4081, #e91e63);
      border:none; color:#fff;
      padding:0.5em 1em; border-radius:25px; cursor:pointer; transition:all 0.3s;
    }
    .dark-toggle:hover { background:#d81b60; }
    .container { padding:2em; max-width:1200px; margin:0 auto; }
    .slider { position:relative; overflow:hidden; border-radius:10px; margin-bottom:2em; }
    .slides { display:flex; transition:transform 0.6s ease; }
    .slides img { width:100%; height:auto; flex-shrink:0; object-fit:cover; border-radius:10px; }
    .slider .prev, .slider .next {
      position:absolute; top:50%; transform:translateY(-50%);
      background:rgba(0,0,0,0.5); color:#fff; border:none; padding:0.6em; cursor:pointer;
      border-radius:50%; z-index:1;
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
    h3 {
      margin-bottom:0.5em; color:#00796b; font-size:1.6em;
      text-shadow:1px 1px 1px #ccc;
      font-family:'Fredoka One', cursive;
    }
    .section p { margin-bottom:1em; line-height:1.6; font-size:1.1em; }
    .cards {
      display:grid; grid-template-columns:repeat(auto-fill,minmax(280px,1fr)); gap:1.5em;
    }
    .card {
      background:linear-gradient(135deg, #ffffff, #e3f2fd);
      border-radius:12px; overflow:hidden;
      box-shadow:0 4px 12px rgba(0,0,0,0.2); transition:transform 0.4s, opacity 0.4s;
      animation:fadeInUp 0.6s ease forwards; opacity:0;
    }
    .card:hover { transform:translateY(-8px); }
    .card img { width:100%; aspect-ratio:1/1; object-fit:cover; }
    .card-content { padding:1em; }
    .card-content h4 {
      margin-bottom:0.5em; color:#0288d1; font-size:1.3em;
      font-family:'Fredoka One', cursive;
    }
    footer {
      text-align:center; padding:1em;
      background:linear-gradient(90deg, #0047ab, #0077ff); color:#fff;
      margin-top:2em; box-shadow:0 -2px 8px rgba(0,0,0,0.2);
    }
    .scroll-top {
      position:fixed; bottom:20px; right:20px;
      background:#009688; color:#fff; border:none;
      padding:0.7em 1em; border-radius:50%; font-size:1.2em; cursor:pointer;
      display:none; z-index:999; transition:background 0.3s;
    }
    .scroll-top:hover { background:#00695c; }
    @keyframes fadeInUp {
      from { transform:translateY(20px); opacity:0; }
      to { transform:translateY(0); opacity:1; }
    }
    @keyframes bounce {
      0%, 100% { transform:translateY(0); }
      50% { transform:translateY(-5px); }
    }
    .fa-horse { color:#ff5722;} .fa-fan{color:#4caf50;} .fa-flag-checkered{color:#2196f3;}
    .fa-kiwi-bird{color:#ff9800;} .fa-rocket{color:#9c27b0;} .fa-water{color:#03a9f4;}
    .fa-frog{color:#8bc34a;} .fa-bicycle{color:#ffeb3b;} .fa-train{color:#673ab7;}
    .fa-battery-full{color:#c2185b;} .fa-circle{color:#009688;}
    .fa-bowling-ball{color:#ff4081;} .fa-crosshairs{color:#607d8b;}
    .fa-tooth{color:#f44336;} .fa-wine-bottle{color:#795548;} .fa-trash-alt{color:#9e9e9e;}
    .fa-theater-masks{color:#3f51b5;} .fa-ring{color:#e91e63;}
  </style>
</head>
<body>
  <div class="color-switcher">
    <button class="color-btn color1" onclick="changeBg('#b2ebf2', '#ffffff', '#fff8e1')">Warna 1</button>
    <button class="color-btn color2" onclick="changeBg('#ffe082', '#fff3e0', '#ffcc80')">Warna 2</button>
    <button class="color-btn color3" onclick="changeBg('#d1c4e9', '#ede7f6', '#b39ddb')">Warna 3</button>
    <button class="color-btn color4" onclick="changeBg('#c8e6c9', '#ffffff', '#a5d6a7')">Warna 4</button>
    <button class="color-btn color5" onclick="changeBg('#ffccbc', '#fff3e0', '#ffab91')">Warna 5</button>
  </div>

  <script>
    function changeBg(color1, color2, color3) {
      document.body.style.background = `linear-gradient(to bottom, ${color1}, ${color2}, ${color3})`;
    }
  </script>
</body>
<!-- Konten lainnya tetap -->


<body>
  <audio id="clickSound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_191c08e103.mp3"></audio>
  <button class="scroll-top" id="scrollTopBtn" onclick="window.scrollTo({top:0, behavior:'smooth'})"><i class="fas fa-arrow-up"></i></button>
  <header>
    <img src="https://i.imgur.com/QntCNNu.png" alt="Logo" class="logo">
    <h2>DINONESIA HARVEST CITY</h2>
    <nav>
      <button class="active" onclick="playSound(); show('beranda')"><i class="fas fa-home"></i> Beranda</button>
      <button onclick="playSound(); show('wahana')"><i class="fas fa-cogs"></i> Wahana</button>
      <button onclick="playSound(); show('permainan')"><i class="fas fa-gamepad"></i> Permainan</button>
      <button onclick="playSound(); show('tentang')"><i class="fas fa-info-circle"></i> Tentang</button>
      <button onclick="playSound(); show('kontak')"><i class="fas fa-phone-alt"></i> Kontak</button>
    </nav>
    <button class="dark-toggle" id="darkBtn"><i class="fas fa-moon"></i> Mode Gelap</button>
  </header>
  <div class="container">
    <div id="beranda" class="content section">
      <div class="slider">
        <div class="slides">
          <img src="https://i.imgur.com/zSS0yQU.jpg"><img src="https://i.imgur.com/MaMryOz.jpg">
          <img src="https://i.imgur.com/MYGFAPQ.jpg"><img src="https://i.imgur.com/omkxG5w.jpg">
          <img src="https://i.imgur.com/r0vKaqP.jpg"><img src="https://i.imgur.com/rgQXi7E.jpg">
        </div>
        <button class="prev" onclick="moveSlide(-1)">❮</button>
        <button class="next" onclick="moveSlide(1)">❯</button>
        <div class="dots"></div>
      </div>
      <p>Jelajahi petualangan prasejarah di <strong>DINONESIA HARVEST CITY</strong>!</p>
    </div>
    <div id="wahana" class="content section" style="display:none;">
      <h3><i class="fas fa-dinosaur"></i> Wahana</h3>
      <div class="cards" id="wahanaCards"></div>
    </div>
    <div id="permainan" class="content section" style="display:none;">
      <h3><i class="fas fa-bowling-ball"></i> Permainan</h3>
      <div class="cards" id="permainanCards"></div>
    </div>
    <div id="tentang" class="content section" style="display:none;">
      <h3><i class="fas fa-info-circle"></i> Tentang</h3>
      <p>
        
        
        
      <section id="wahana-dinonesia" class="p-6 bg-white dark:bg-gray-900 text-gray-800 dark:text-white">
        <div class="max-w-4xl mx-auto">
          <h2 class="text-3xl font-bold mb-4 text-center">🌋 Wahana Dinonesia: Petualangan Seru di Zaman Dinosaurus!</h2>
          <p class="mb-6 text-justify">
            Selamat datang di <strong>Dinonesia</strong>, taman hiburan edukatif yang menghadirkan dunia prasejarah dalam balutan wahana seru dan interaktif! Di sini, anak-anak dan keluarga diajak menjelajahi kehidupan dinosaurus lewat berbagai permainan dan atraksi menarik yang tak hanya menghibur, tetapi juga mendidik.
          </p>
          <p class="mb-6 text-justify">
            <strong>Setiap wahana di Dinonesia dirancang dengan tema unik, karakter dino yang lucu, serta teknologi modern</strong> seperti efek suara, animasi, dan sensor interaktif untuk menciptakan pengalaman yang tak terlupakan.
          </p>

          <h3 class="text-2xl font-semibold mb-2 mt-8">🎢 Kategori Wahana Utama:</h3>
          <ul class="list-disc pl-6 space-y-1">
            <li><strong>Dino Ride</strong> – Naiki dinosaurus favoritmu dan berkeliling di lintasan mini yang seru dan aman!</li>
            <li><strong>Dino Swing</strong> – Ayunan besar berbentuk dinosaurus yang mengayun ke kiri dan kanan sambil memutar.</li>
            <li><strong>Merry Go Round</strong> – Komidi putar penuh warna dengan hewan-hewan purba yang ramah.</li>
            <li><strong>Dino Hopper</strong> – Wahana loncat-loncat dengan efek pantulan yang membuat anak-anak tertawa riang.</li>
            <li><strong>Speed Racing</strong> – Arena balapan mini dengan mobil-mobil bergambar dinosaurus.</li>
            <li><strong>Sky Race</strong> – Terbang di udara dengan baling-baling berdesain pterodactyl, cocok untuk si kecil yang suka petualangan.</li>
            <li><strong>Magic Bike</strong> – Sepeda melayang yang dikayuh di udara dengan tampilan taman dino dari ketinggian.</li>
            <li><strong>Choochoo Train</strong> – Kereta mini yang membawa penumpang kecil menjelajahi area Dino Village.</li>
            <li><strong>Cano River</strong> – Petualangan air menyusuri sungai tenang di antara replika hutan purba.</li>
            <li><strong>Batrey Bike</strong> – Sepeda listrik dengan desain dino yang bisa dikendarai anak-anak.</li>
            <li><strong>Ferris Wheel</strong> – Roda raksasa dengan kabin bertema telur dinosaurus yang bisa melihat seluruh area dari atas.</li>
          </ul>

          <h3 class="text-2xl font-semibold mb-2 mt-8">🎯 Permainan Edukatif & Karnaval:</h3>
          <ul class="list-disc pl-6 space-y-1">
            <li><strong>Fun Bowling</strong> – Menjatuhkan pin dinosaurus dengan bola warna-warni.</li>
            <li><strong>Smash the Clown</strong> – Pukul karakter dino badut yang muncul tiba-tiba.</li>
            <li><strong>Duck Ring Toss</strong> – Lempar cincin ke leher bebek sambil belajar warna dan koordinasi.</li>
            <li><strong>Jungle Hunting</strong> – Tantangan membidik target di hutan dinosaurus.</li>
            <li><strong>Crazy Bottle</strong> & <strong>Crazy Teeth</strong> – Latih konsentrasi dan ketangkasan!</li>
            <li><strong>Smash Can</strong> – Jatuhkan kaleng-kaleng purba untuk memenangkan hadiah!</li>
          </ul>

          <h3 class="text-2xl font-semibold mb-2 mt-8">🎧 Fitur Pendukung:</h3>
          <ul class="list-disc pl-6 space-y-1 mb-8">
            <li><strong>Narasi edukatif dan musik latar taman</strong> untuk menambah nuansa petualangan.</li>
            <li><strong>Peta interaktif</strong> untuk menjelajahi lokasi wahana.</li>
            <li><strong>Mode Gelap</strong> agar tampilan lebih nyaman di malam hari atau dalam ruangan.</li>
          </ul>
        </div>
      </section>
      
      </p>
    </div>
    <div id="kontak" class="content section" style="display:none;">
      <h3><i class="fas fa-phone-alt"></i> Kontak</h3>
      <p>Email: info@dinonesia.com | Tel: (021) 123-4567</p>
      <section id="tentang" style="padding: 60px 30px; background-color: #e8f5e9; border-radius: 16px; max-width: 960px; margin: 40px auto; box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1); font-family: Arial, sans-serif;">
  <div style="text-align: center;">
    <img src="https://i.imgur.com/V8pThH2.jpg" alt="Foto Profil Adnan Fauzi" style="width: 150px; height: 150px; border-radius: 50%; border: 4px solid #fff; object-fit: cover; background-color: white; box-shadow: 0 4px 10px rgba(0,0,0,0.2);">
    <h2 style="font-size: 2.2em; color: #2c5364; margin-top: 20px;">Adnan Fauzi</h2>
    <p style="font-size: 1.1em; color: #555;">Manajer Proyek | Pemimpin Tim | Komunikator Efektif</p>
  </div>

  <div style="margin-top: 40px;">
    <h3 style="font-size: 1.5em; color: #2e7d32; border-left: 5px solid #66bb6a; padding-left: 12px; margin-bottom: 15px;">Tentang Saya</h3>
    <p style="color: #333; line-height: 1.7;">
      Saya Adnan Fauzi, seorang profesional yang berdedikasi dengan pengalaman lebih dari 10 tahun dalam memimpin tim dan mengelola proyek. Keahlian saya terletak pada kepemimpinan strategis, komunikasi efektif, dan kemampuan menyelesaikan masalah dengan pendekatan kreatif dan sistematis.
    </p>

    <div style="margin-top: 30px; text-align: center;">
      <button onclick="toggleMusic()" style="background-color: #388e3c; color: white; border: none; padding: 10px 22px; border-radius: 8px; font-size: 16px; cursor: pointer;">
        🎵 Putar Musik
      </button>
    </div>

    <audio id="cvMusic" loop>
      <source src="musik-cv.mp3" type="audio/mpeg">
      Browser Anda tidak mendukung pemutar audio.
    </audio>
  </div>
</section>

    </div>
  </div>
  <footer>
    <p>© 2025 DINONESIA HARVEST CITY</p>
  </footer>
  <script>
    function playSound() {
      document.getElementById('clickSound').play();
    }

    function show(section) {
      document.querySelectorAll('.content').forEach(c => c.style.display = 'none');
      document.getElementById(section).style.display = 'block';
      document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
      event.currentTarget.classList.add('active');
    }
    document.getElementById('darkBtn').addEventListener('click', () => document.body.classList.toggle('dark-mode'));
    window.addEventListener('scroll', () => {
      document.getElementById('scrollTopBtn').style.display = window.scrollY > 50 ? 'block' : 'none'
    });
    const wahanaData = [{
      name: 'Merry Go Round',
      icon: 'fas fa-horse',
      image: 'https://i.imgur.com/v295uLu.jpg'
    }, {
      name: 'Dino Swing',
      icon: 'fas fa-fan',
      image: 'https://i.imgur.com/gnN3IE2.jpg'
    }, {
      name: 'Speed Racing',
      icon: 'fas fa-flag-checkered',
      image: 'https://i.imgur.com/sitgGS1.jpg'
    }, {
      name: 'Dino Ride',
      icon: 'fas fa-kiwi-bird',
      image: 'https://i.imgur.com/ygC3mFW.jpg'
    }, {
      name: 'Sky Race',
      icon: 'fas fa-rocket',
      image: 'https://i.imgur.com/D9eEQVz.jpg'
    }, {
      name: 'Cano River',
      icon: 'fas fa-water',
      image: 'https://i.imgur.com/GJMj8Lc.jpg'
    }, {
      name: 'Dino Hopper',
      icon: 'fas fa-frog',
      image: 'https://i.imgur.com/YvnYuGL.png?1'
    }, {
      name: 'Magic Bike',
      icon: 'fas fa-bicycle',
      image: 'https://i.imgur.com/d9IC7rZ.jpg'
    }, {
      name: 'Choochoo Train',
      icon: 'fas fa-train',
      image: 'https://i.imgur.com/8pAThVW.jpg'
    }, {
      name: 'Battery Bike',
      icon: 'fas fa-battery-full',
      image: 'https://i.imgur.com/d9IC7rZ.jpg'
    }, {
      name: 'Ferris Wheel',
      icon: 'fas fa-circle',
      image: 'https://i.imgur.com/wUIAhpJ.jpg'
    }];
    const permainanData = [{
      name: 'Fun Bowling',
      icon: 'fas fa-bowling-ball',
      image: 'https://i.imgur.com/sfldgAD.jpg'
    }, {
      name: 'Jungle Hunting',
      icon: 'fas fa-crosshairs',
      image: 'https://i.imgur.com/mxtaBYp.jpg'
    }, {
      name: 'Crazy Teeth',
      icon: 'fas fa-tooth',
      image: 'https://i.imgur.com/gFjETMO.jpg'
    }, {
      name: 'Crazy Bottle',
      icon: 'fas fa-wine-bottle',
      image: 'https://i.imgur.com/50N08iz.jpg'
    }, {
      name: 'Smash Can',
      icon: 'fas fa-trash-alt',
      image: 'https://i.imgur.com/smY6JGG.jpg'
    }, {
      name: 'Smash the Clown',
      icon: 'fas fa-theater-masks',
      image: 'https://i.imgur.com/ayLtifR.jpg'
    }, {
      name: 'Duck Ring Toss',
      icon: 'fas fa-ring',
      image: 'https://i.imgur.com/9v30JSh.jpg'
    }];

    function generateCards(data, id) {
      const c = document.getElementById(id);
      c.innerHTML = '';
      data.forEach(it => {
        const card = document.createElement('div');
        card.className = 'card';
        card.innerHTML = `<img src="${it.image}"><div class="card-content"><h4><i class="${it.icon}"></i> ${it.name}</h4></div>`;
        c.appendChild(card);
      });
    }
    generateCards(wahanaData, 'wahanaCards');
    generateCards(permainanData, 'permainanCards');
    let slideIndex = 0;
    const slides = document.querySelectorAll('.slides img'),
      dotsContainer = document.querySelector('.dots');

    function updateDots() {
      document.querySelectorAll('.dot').forEach((d, i) => d.classList.toggle('active', i === slideIndex));
    }

    function showSlide(idx) {
      slideIndex = (idx + slides.length) % slides.length;
      document.querySelector('.slides').style.transform = `translateX(-${slideIndex*100}%)`;
      updateDots();
    }

    function moveSlide(step) {
      showSlide(slideIndex + step);
    }
    setInterval(() => showSlide(slideIndex + 1), 5000);
    showSlide(0);
    
  </script>
  
</body>

</html>
