<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Portal Sastra — Serli SA</title>
  <meta name="description" content="Kumpulan cerpen & puisi — Serli SA" />
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' fill='%23f8efe6'/><text x='50' y='60' font-size='50' text-anchor='middle' fill='%236b4a36' font-family='serif'>S</text></svg>">
  <style>
    /* Reset-ish */
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family: Georgia, 'Times New Roman', serif;background:#f5efe6;color:#2b2b2b}

    /* Vintage textured background */
    body::before{
      content:'';position:fixed;inset:0;z-index:-2;background:linear-gradient(180deg,#f6efe6 0%,#efe6dd 100%);
      background-blend-mode:multiply;opacity:1;
    }
    body::after{
      content:'';position:fixed;inset:0;z-index:-1;pointer-events:none;background-image:radial-gradient(rgba(0,0,0,0.02) 1px, transparent 1px);background-size:18px 18px;opacity:0.7;}

    header{display:flex;align-items:center;gap:18px;padding:18px 24px;border-bottom:1px solid rgba(43,43,43,0.06);background:linear-gradient(180deg, rgba(255,255,255,0.6), rgba(255,255,255,0.45));backdrop-filter: blur(2px)}
    .brand{display:flex;align-items:center;gap:14px}
    .logo{width:56px;height:56px;border-radius:8px;background:#f2e9df;display:flex;align-items:center;justify-content:center;border:1px solid rgba(0,0,0,0.06)}
    .logo strong{font-family: Georgia, serif;font-size:28px;color:#5b3f2f}
    nav{margin-left:auto}
    nav ul{display:flex;gap:12px;list-style:none;margin:0;padding:0}
    nav a{display:inline-block;padding:8px 12px;border-radius:8px;text-decoration:none;color:#442e23}
    nav a.active{background:#e9dbc9;box-shadow:0 2px 0 rgba(0,0,0,0.04)}

    main{display:grid;grid-template-columns:340px 1fr;gap:20px;padding:28px;align-items:start}

    /* Left panel */
    .panel{background:rgba(255,255,255,0.6);border-radius:12px;padding:14px;border:1px solid rgba(43,43,43,0.04)}
    .section-title{font-weight:700;color:#5b3f2f;margin:6px 0 12px}
    .list{display:flex;flex-direction:column;gap:10px;max-height:70vh;overflow:auto;padding-right:6px}
    .item{display:flex;gap:12px;align-items:center;cursor:pointer;padding:8px;border-radius:8px}
    .item:hover{background:rgba(90,56,36,0.04)}
    .thumb{width:64px;height:64px;border-radius:6px;flex-shrink:0;object-fit:cover;border:1px solid rgba(0,0,0,0.04)}
    .meta{flex:1}
    .meta h4{margin:0;font-size:15px}
    .meta p{margin:3px 0 0;font-size:12px;color:#6b4f3e}

    /* Right content */
    .content{background:rgba(255,255,255,0.7);padding:22px;border-radius:12px;border:1px solid rgba(43,43,43,0.04);min-height:60vh}
    .content h2{margin-top:0;color:#4a3124}
    .byline{font-size:13px;color:#6b4f3e;margin-bottom:12px}

    /* Story text area - attempt to disable selection/copy */
    .story-text{line-height:1.8;font-size:16px;white-space:pre-wrap;user-select:none;-webkit-user-select:none;-moz-user-select:none;pointer-events:auto}
    .story-overlay{position:absolute;inset:0;pointer-events:none}

    footer{padding:20px;text-align:center;color:#6b4f3e;font-size:14px}

    /* Buttons */
    .btn{display:inline-block;padding:8px 14px;border-radius:10px;text-decoration:none;font-weight:600}
    .btn-primary{background:#7a5138;color:#fff}
    .btn-ghost{background:transparent;border:1px solid rgba(74,49,36,0.08);color:#5b3f2f}

    /* About card */
    .about p{margin:6px 0}

    /* Responsive */
    @media (max-width:880px){main{grid-template-columns:1fr;padding:18px}nav ul{display:none} .list{max-height:220px}}

    /* small notice */
    .notice{font-size:12px;color:#6b4f3e;margin-top:8px}
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo"><strong>S</strong></div>
      <div>
        <div style="font-weight:700;color:#5b3f2f">Portal Sastra — Serli SA</div>
        <div style="font-size:12px;color:#7a5a4a">Cerpen dan puisi — klasik & vintage</div>
      </div>
    </div>

    <nav>
      <ul>
        <li><a href="#home" class="nav-link active" data-target="home">Home</a></li>
        <li><a href="#cerpen" class="nav-link" data-target="cerpen">Kumpulan Cerpen</a></li>
        <li><a href="#puisi" class="nav-link" data-target="puisi">Kumpulan Puisi</a></li>
        <li><a href="#saweran" class="nav-link" data-target="saweran">Saweran</a></li>
        <li><a href="#about" class="nav-link" data-target="about">Tentang Penulis</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <!-- Left: lists -->
    <aside class="panel">
      <div class="section">
        <div class="section-title">Kumpulan Cerpen</div>
        <div class="list" id="cerpen-list"></div>
      </div>
      <hr style="margin:14px 0;border:none;border-top:1px dashed rgba(0,0,0,0.04)">
      <div class="section">
        <div class="section-title">Kumpulan Puisi</div>
        <div class="list" id="puisi-list"></div>
      </div>
      <div style="margin-top:12px">
        <a class="btn btn-primary" id="donate-btn" href="https://saweria.co/serlisa20" target="_blank" rel="noopener noreferrer">Saweran ke Serli SA</a>
        <div class="notice">Catatan: demi kenyamanan pembaca, teks tidak bisa disalin.</div>
      </div>
    </aside>

    <!-- Right: content display -->
    <section class="content" id="content-area">
      <h2 id="content-title">Selamat datang</h2>
      <div class="byline">Portal pribadi Serli SA — cerpen & puisi</div>
      <div id="content-body">
        <p>Halo — ini portal sastra untuk karya-karya Serli SA. Pilih salah satu judul di panel kiri untuk membaca. Karya tidak dapat diedit oleh pengunjung. Jika ingin menghubungi atau membeli karya, gunakan tombol Saweran atau hubungi penulis.</p>

        <div class="about" style="margin-top:18px">
          <h3>Tentang Penulis</h3>
          <p><strong>Nama pena:</strong> Serli SA</p>
          <p><strong>Tanggal lahir:</strong> 20 Desember 2004</p>
          <p><strong>Domisili:</strong> Palangka Raya</p>
          <p><strong>Latar pendidikan sastra:</strong> mulai menempuh sastra sejak kelas 3 MTS</p>
          <p class="notice"><em>Perhatian:</em> sistem berusaha mencegah penyalinan teks (copy/paste) dan pemilihan teks di browser. Namun kami tidak dapat sepenuhnya mencegah pengambilan screenshot — itu tergantung perangkat pengunjung.</p>
        </div>
      </div>
    </section>
  </main>

  <footer>
    © Serli SA — Portal Sastra • Dipublikasikan untuk pembaca umum
  </footer>

  <script>
    // ===== Data: ganti sesuai kebutuhan =====
    const cerpenData = [
      {id: 'c1', title: 'Kapal di Halaman Belakang', thumb: '', excerpt: 'Sebuah kapal kecil yang terdampar di halaman...' , text: `Kapal itu terdampar di halaman belakang rumahku.

Ia kecil — bukan kapal sungguhan, tapi mainan kayu yang kutemukan terbenam di rumput. Waktu aku sentuh, bau laut seketika mengisi napasku, padahal kami jauh dari pelabuhan.

(Substitusi cerita singkat untuk demo.)`},
      {id: 'c2', title: 'Malam pada Kalender Tua', thumb: '', excerpt: 'Ketika kalender lama tergulung, malam pun turut menganga...' , text: `Kalender tua terlipat di meja. Angka-angka jatuh seperti daun.

Aku membaca nama-nama yang tak kusangka akan kembali, dan malam tiba-tiba terasa sangat panjang.`}
    ];

    const puisiData = [
      {id: 'p1', title: 'Puisi Biru', thumb: '', excerpt: 'Biru, seperti halaman yang belum ditulis...' , text: `Biru.
Lembaran yang malu pada pena.

Kita menulis bahasa pelan, sampai pagi membawa kembali kata.`},
      {id: 'p2', title: 'Doa yang Tersisa', thumb: '', excerpt: 'Doa pendek yang ia titipkan pada jendela...' , text: `Kupintal doa di ujung selimut.
Ia hangat, namun tak cukup untuk mengusir dingin.`}
    ];

    // helper: create thumbnail SVG as data URL (vintage)
    function makeThumb(title){
      const escaped = title.replace(/&/g,'%26');
      const svg = `data:image/svg+xml;utf8,` + encodeURIComponent(`
        <svg xmlns='http://www.w3.org/2000/svg' width='200' height='120'>
          <rect width='100%' height='100%' fill='%23efe1d1'/>
          <text x='50%' y='50%' dominant-baseline='middle' text-anchor='middle' font-family='Georgia,serif' font-size='18' fill='%235b3f2f'>${escaped}</text>
        </svg>
      `);
      return svg;
    }

    // populate lists
    const cerpenList = document.getElementById('cerpen-list');
    const puisiList = document.getElementById('puisi-list');

    function makeListItem(item, type){
      const el = document.createElement('div'); el.className='item'; el.dataset.id = item.id; el.dataset.type = type;
      const img = document.createElement('img'); img.className='thumb'; img.src = item.thumb || makeThumb(item.title);
      const meta = document.createElement('div'); meta.className='meta';
      const h = document.createElement('h4'); h.textContent = item.title;
      const p = document.createElement('p'); p.textContent = item.excerpt;
      meta.appendChild(h); meta.appendChild(p);
      el.appendChild(img); el.appendChild(meta);
      el.addEventListener('click', ()=> showContent(item, type));
      return el;
    }

    cerpenData.forEach(i=> cerpenList.appendChild(makeListItem(i,'cerpen')));
    puisiData.forEach(i=> puisiList.appendChild(makeListItem(i,'puisi')));

    // show content in right pane (does NOT open modal / does not cover lists)
    const contentTitle = document.getElementById('content-title');
    const contentBody = document.getElementById('content-body');

    function showContent(item, type){
      // clear body then insert
      contentTitle.textContent = item.title + (type==='cerpen' ? ' — Cerpen' : ' — Puisi');
      contentBody.innerHTML = '';

      const by = document.createElement('div'); by.className='byline'; by.textContent = `Penulis: Serli SA • ${type==='cerpen' ? 'Cerpen' : 'Puisi'}`;
      const img = document.createElement('img'); img.src = item.thumb || makeThumb(item.title); img.style.width='100%'; img.style.maxHeight='260px'; img.style.objectFit='cover'; img.style.borderRadius='10px'; img.style.marginBottom='12px';
      const textWrap = document.createElement('div'); textWrap.style.position='relative';
      const t = document.createElement('div'); t.className='story-text'; t.textContent = item.text;
      // Add a translucent overlay (pointer-events none) so text isn't easily selectable when dragging quickly
      const overlay = document.createElement('div'); overlay.className='story-overlay';

      textWrap.appendChild(t); textWrap.appendChild(overlay);
      contentBody.appendChild(by); contentBody.appendChild(img); contentBody.appendChild(textWrap);

      // update URL hash so nav reflects
      history.replaceState(null,'',`#${item.id}`);
    }

    // nav links
    const navLinks = document.querySelectorAll('.nav-link');
    navLinks.forEach(a=> a.addEventListener('click', (e)=>{
      e.preventDefault(); navLinks.forEach(x=>x.classList.remove('active')); a.classList.add('active');
      const target = a.dataset.target;
      // scroll to top and show appropriate content
      if(target==='home'){
        contentTitle.textContent = 'Selamat datang';
        contentBody.innerHTML = `<p>Halo — ini portal sastra untuk karya-karya Serli SA. Pilih salah satu judul di panel kiri untuk membaca. Karya tidak dapat diedit oleh pengunjung. Jika ingin menghubungi atau membeli karya, gunakan tombol Saweran atau hubungi penulis.</p>`;
      } else if(target==='cerpen'){
        // focus cerpen list
        document.getElementById('cerpen-list').scrollIntoView({behavior:'smooth', block:'center'});
      } else if(target==='puisi'){
        document.getElementById('puisi-list').scrollIntoView({behavior:'smooth', block:'center'});
      } else if(target==='saweran'){
        window.open('https://saweria.co/serlisa20','_blank','noopener');
      } else if(target==='about'){
        contentTitle.textContent = 'Tentang Penulis';
        contentBody.innerHTML = `<div class="about"><p><strong>Nama pena:</strong> Serli SA</p><p><strong>Tanggal lahir:</strong> 20 Desember 2004</p><p><strong>Domisili:</strong> Palangka Raya</p><p><strong>Latar pendidikan:</strong> Menempuh sastra sejak kelas 3 MTS</p><p class="notice"><em>Perhatian:</em> teks pada portal ini berusaha dicegah untuk disalin. Screenshot tidak bisa dijamin aman.</p></div>`;
      }
      window.scrollTo({top:0,behavior:'smooth'});
    }));

    // Try to block common copy actions (best-effort)
    document.addEventListener('copy', (e)=>{
      e.preventDefault();
      // some browsers require setting clipboardData
      try{ e.clipboardData.setData('text/plain',''); }catch(err){}
      alert('Menyalin teks dinonaktifkan di portal ini. Jika ingin mengutip, hubungi penulis.');
    });

    document.addEventListener('contextmenu', (e)=>{
      // allow context menu when clicking outside story-text? we simply disable globally to be strict
      e.preventDefault();
    });

    document.addEventListener('keydown', (e)=>{
      // block Ctrl/Cmd + C, A, S (save), U (view source) — best-effort but cannot stop determined users
      if((e.ctrlKey||e.metaKey) && ['c','a','s','u','p'].includes(e.key.toLowerCase())){
        e.preventDefault();
        alert('Aksi keyboard dinonaktifkan di portal ini. Hubungi penulis jika perlu akses.');
      }
      // try catch PrintScreen key (cannot reliably prevent)
      if(e.key && e.key.toLowerCase().includes('printscreen')){
        alert('Screenshot tidak dapat dijamin. Mohon menghormati hak cipta penulis.');
      }
    });

    // Prevent drag selection on story text
    document.addEventListener('selectstart', (e)=>{
      const el = e.target; if(el.closest && el.closest('.story-text')) e.preventDefault();
    });

    // Disable editing features
    document.querySelectorAll('a').forEach(a=>{ a.setAttribute('draggable','false'); });

    // On load: if hash points to a story, open it
    window.addEventListener('load', ()=>{
      const h = location.hash.replace('#','');
      if(h){
        const found = [...cerpenData, ...puisiData].find(x=>x.id===h);
        if(found) showContent(found, cerpenData.find(c=>c.id===h)?'cerpen':'puisi');
      }
    });

    // Accessibility: allow keyboard navigation of lists
    document.querySelectorAll('.list').forEach(list=>{
      list.addEventListener('keydown', (e)=>{
        const items = Array.from(list.querySelectorAll('.item'));
        const idx = items.indexOf(document.activeElement.closest('.item'));
        if(e.key==='ArrowDown'){ e.preventDefault(); items[Math.min(items.length-1, (idx+1)||0)].focus(); }
        if(e.key==='ArrowUp'){ e.preventDefault(); items[Math.max(0, (idx-1)||0)].focus(); }
      });
      // make items focusable
      list.querySelectorAll('.item').forEach(it=>{ it.setAttribute('tabindex','0'); });
    });

  </script>
</body>
</html>
