<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Portfolio — Video Editor & Graphic Designer</title>
  <meta name="description" content="Portfolio website for a creative video editor and graphic designer. Showreel, projects, services, and contact." />

  <!-- Fonts & Icons (Free CDNs) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" integrity="sha512-wxM6p9M1aW4N3F5wO1N8q3m7yq8g8o0N1adn0m3aQ3tK7t7yq0y+2Qv2xj2e" crossorigin="anonymous" referrerpolicy="no-referrer" />

  <style>
    :root{
      --bg:#0f1115;    /* deep slate */
      --card:#151922;  /* card */
      --muted:#a5b0c2; /* text-muted */
      --text:#e8ecf3;  /* text */
      --brand:#6ee7f9; /* accent */
      --brand-2:#a78bfa; /* accent 2 */
      --shadow:0 10px 30px rgba(0,0,0,.3);
      --radius:18px;
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{margin:0;font-family:Poppins,system-ui,-apple-system,Segoe UI,Roboto; background:radial-gradient(1200px 600px at 80% -10%, rgba(167,139,250,.15), transparent), radial-gradient(1000px 500px at -10% 10%, rgba(110,231,249,.12), transparent), var(--bg); color:var(--text)}

    /* Navbar */
    .nav{position:sticky;top:0;z-index:20;backdrop-filter:blur(8px);background:rgba(15,17,21,.7);border-bottom:1px solid rgba(255,255,255,.06)}
    .nav-wrap{max-width:1200px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;padding:14px 20px}
    .brand{display:flex;gap:10px;align-items:center;font-weight:700;letter-spacing:.5px}
    .brand .dot{width:10px;height:10px;border-radius:50%;background:linear-gradient(135deg,var(--brand),var(--brand-2));box-shadow:0 0 20px rgba(110,231,249,.8)}
    .nav a{color:var(--text);text-decoration:none;opacity:.85}
    .menu{display:flex;gap:22px}
    .menu a{font-weight:500}
    .menu a:hover{opacity:1}

    /* Hero */
    .hero{max-width:1200px;margin:0 auto;padding:70px 20px 40px;display:grid;grid-template-columns:1.2fr .8fr;gap:40px;align-items:center}
    .badge{display:inline-flex;gap:8px;align-items:center;padding:6px 10px;border:1px solid rgba(255,255,255,.1);border-radius:999px;color:var(--muted);font-size:12px}
    .badge i{color:var(--brand)}
    h1{font-size:44px;line-height:1.1;margin:16px 0}
    .lead{color:var(--muted);font-weight:400}
    .cta{margin-top:22px;display:flex;gap:12px;flex-wrap:wrap}
    .btn{padding:12px 18px;border-radius:12px;border:1px solid rgba(255,255,255,.12);color:var(--text);text-decoration:none;display:inline-flex;gap:10px;align-items:center;font-weight:600}
    .btn-primary{background:linear-gradient(135deg,var(--brand),var(--brand-2));border-color:transparent;color:#0b1020}
    .btn:hover{transform:translateY(-2px);box-shadow:var(--shadow)}
    .hero-card{background:linear-gradient(145deg,rgba(255,255,255,.06),rgba(255,255,255,.03));border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);overflow:hidden}
    .showreel{aspect-ratio:16/9;width:100%;display:block}

    /* Sections */
    section{max-width:1200px;margin:0 auto;padding:60px 20px}
    .section-title{display:flex;align-items:center;gap:12px;margin-bottom:20px}
    .section-title .line{height:1px;flex:1;background:linear-gradient(90deg,transparent,rgba(255,255,255,.2),transparent)}

    /* Services */
    .grid{display:grid;gap:18px}
    .services{grid-template-columns:repeat(3,minmax(0,1fr))}
    .card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:16px;padding:22px;box-shadow:var(--shadow)}
    .card i{font-size:22px;color:var(--brand)}
    .card h3{margin:10px 0 6px}
    .card p{color:var(--muted);font-size:14px;margin:0}

    /* Portfolio */
    .filters{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:18px}
    .filter{padding:8px 12px;border-radius:999px;border:1px solid rgba(255,255,255,.1);background:transparent;color:var(--text);cursor:pointer}
    .filter.active{background:rgba(110,231,249,.12);border-color:rgba(110,231,249,.4)}
    .portfolio{grid-template-columns:repeat(3,minmax(0,1fr))}
    .tile{position:relative;border-radius:14px;overflow:hidden;border:1px solid rgba(255,255,255,.06);background:#0c0f14}
    .tile img,.tile video{display:block;width:100%;height:220px;object-fit:cover}
    .tile .meta{position:absolute;inset:auto 0 0 0;padding:12px;background:linear-gradient(180deg,transparent,rgba(0,0,0,.7));display:flex;justify-content:space-between;align-items:end}
    .chip{font-size:12px;padding:6px 10px;border-radius:999px;background:rgba(255,255,255,.12)}
    .tile:hover{transform:translateY(-3px);box-shadow:var(--shadow)}

    /* Testimonials */
    .testimonials{grid-template-columns:repeat(3,minmax(0,1fr))}
    .avatar{width:36px;height:36px;border-radius:50%;object-fit:cover;margin-right:10px}
    .quote{color:var(--muted);font-size:14px}

    /* About */
    .about-wrap{display:grid;grid-template-columns:1fr 1fr;gap:24px}
    .about-card{border-left:3px solid var(--brand);}
    .facts{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
    .fact{background:linear-gradient(145deg,rgba(255,255,255,.05),rgba(255,255,255,.02));border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:14px;text-align:center}
    .fact strong{font-size:22px;display:block}

    /* Contact */
    .contact{display:grid;grid-template-columns:1.2fr .8fr;gap:24px}
    form{display:grid;gap:12px}
    input, textarea{width:100%;padding:12px 14px;border-radius:12px;border:1px solid rgba(255,255,255,.1);background:#0b0f15;color:var(--text)}
    textarea{min-height:120px}
    .small{font-size:12px;color:var(--muted)}

    /* Footer */
    footer{border-top:1px solid rgba(255,255,255,.08);color:var(--muted);padding:28px 20px;text-align:center}
    .social{display:flex;gap:14px;justify-content:center;margin-top:8px}
    .social a{color:var(--muted)}

    /* Responsive */
    @media (max-width: 980px){
      .hero{grid-template-columns:1fr}
      .portfolio{grid-template-columns:repeat(2,minmax(0,1fr))}
      .services,.testimonials{grid-template-columns:repeat(2,minmax(0,1fr))}
      .about-wrap,.contact{grid-template-columns:1fr}
    }
    @media (max-width: 640px){
      h1{font-size:34px}
      .portfolio{grid-template-columns:1fr}
      .services,.testimonials{grid-template-columns:1fr}
    }
  </style>
</head>
<body>
  <header class="nav">
    <div class="nav-wrap">
      <a class="brand" href="#top"><span class="dot"></span> <span id="brandName">Your Name</span></a>
      <nav class="menu">
        <a href="#work">Work</a>
        <a href="#services">Services</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <main id="top">
    <!-- HERO -->
    <section class="hero">
      <div>
        <span class="badge"><i class="fa-solid fa-clapperboard"></i> Video Editor • Graphic Designer</span>
        <h1>Crafting sharp edits & clean visuals that tell your story.</h1>
        <p class="lead">I help brands, creators, and startups turn raw footage and ideas into scroll-stopping content — from cinematic reels to polished brand design.</p>
        <div class="cta">
          <a class="btn btn-primary" href="#work"><i class="fa-solid fa-play"></i> View Work</a>
          <a class="btn" href="#contact"><i class="fa-solid fa-paper-plane"></i> Let's Collaborate</a>
          <a class="btn" target="_blank" href="#" id="resumeLink"><i class="fa-solid fa-file-arrow-down"></i> Download Resume</a>
        </div>
      </div>
      <div class="hero-card">
        <!-- Replace the src with your hosted showreel link (YouTube/Vimeo/MP4) -->
        <video class="showreel" src="https://storage.googleapis.com/gtv-videos-bucket/sample/ForBiggerJoyrides.mp4" controls poster="https://images.unsplash.com/photo-1510511459019-5dda7724fd87?q=80&w=1200&auto=format&fit=crop">
          Your browser does not support the video tag.
        </video>
      </div>
    </section>

    <!-- WORK / PORTFOLIO -->
    <section id="work">
      <div class="section-title">
        <h2>Selected Work</h2>
        <div class="line"></div>
      </div>

      <div class="filters" id="filters">
        <button class="filter active" data-filter="all">All</button>
        <button class="filter" data-filter="video">Video</button>
        <button class="filter" data-filter="design">Design</button>
        <button class="filter" data-filter="branding">Branding</button>
      </div>

      <div class="grid portfolio" id="portfolio">
        <!-- Example tiles (replace with your projects) -->
        <article class="tile" data-type="video" tabindex="0" aria-label="Product Ad – 15s Reel">
          <video src="https://storage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4" muted loop playsinline></video>
          <div class="meta">
            <div>
              <strong>Product Ad – 15s Reel</strong>
              <div class="small">Editing • Color • SFX</div>
            </div>
            <span class="chip">Video</span>
          </div>
        </article>

        <article class="tile" data-type="design" tabindex="0" aria-label="Poster Series">
          <img src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=1400&auto=format&fit=crop" alt="Poster design preview"/>
          <div class="meta">
            <div>
              <strong>Poster Series</strong>
              <div class="small">Typography • Layout • Print</div>
            </div>
            <span class="chip">Design</span>
          </div>
        </article>

        <article class="tile" data-type="branding" tabindex="0" aria-label="Logo Identity Refresh">
          <img src="https://images.unsplash.com/photo-1606326608606-aa0b62935fbb?q=80&w=1400&auto=format&fit=crop" alt="Branding mockup"/>
          <div class="meta">
            <div>
              <strong>Logo Identity Refresh</strong>
              <div class="small">Mark • Palette • System</div>
            </div>
            <span class="chip">Branding</span>
          </div>
        </article>

        <article class="tile" data-type="video" tabindex="0" aria-label="YouTube Edit – Travel Vlog">
          <img src="https://images.unsplash.com/photo-1491553895911-0055eca6402d?q=80&w=1400&auto=format&fit=crop" alt="Travel edit thumbnail"/>
          <div class="meta">
            <div>
              <strong>YouTube Edit – Travel Vlog</strong>
              <div class="small">Cut • Music • Titles</div>
            </div>
            <span class="chip">Video</span>
          </div>
        </article>

        <article class="tile" data-type="design" tabindex="0" aria-label="Social Carousel Set">
          <img src="https://images.unsplash.com/photo-1557683316-973673baf926?q=80&w=1400&auto=format&fit=crop" alt="Carousel design thumbnails"/>
          <div class="meta">
            <div>
              <strong>Social Carousel Set</strong>
              <div class="small">IG • FB • LinkedIn</div>
            </div>
            <span class="chip">Design</span>
          </div>
        </article>

        <article class="tile" data-type="branding" tabindex="0" aria-label="Packaging Concept">
          <img src="https://images.unsplash.com/photo-1549923746-c502d488b3ea?q=80&w=1400&auto=format&fit=crop" alt="Packaging concept"/>
          <div class="meta">
            <div>
              <strong>Packaging Concept</strong>
              <div class="small">3D Mock • Dielines</div>
            </div>
            <span class="chip">Branding</span>
          </div>
        </article>
      </div>
    </section>

    <!-- SERVICES -->
    <section id="services">
      <div class="section-title">
        <h2>Services</h2>
        <div class="line"></div>
      </div>
      <div class="grid services">
        <div class="card">
          <i class="fa-solid fa-film"></i>
          <h3>Video Editing</h3>
          <p>Shorts/Reels, YouTube videos, ads, documentaries. Color grading, sound design, motion graphics, subtitles.</p>
        </div>
        <div class="card">
          <i class="fa-solid fa-pen-ruler"></i>
          <h3>Graphic Design</h3>
          <p>Branding, posters, social carousels, thumbnails, presentations, print-ready artwork, web creatives.</p>
        </div>
        <div class="card">
          <i class="fa-solid fa-wand-magic-sparkles"></i>
          <h3>Motion & Titles</h3>
          <p>Logo stings, lower thirds, animated explainers, lyric videos, kinetic typography, GIFs.</p>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about">
      <div class="section-title">
        <h2>About</h2>
        <div class="line"></div>
      </div>
      <div class="about-wrap">
        <div class="card about-card">
          <h3 id="yourName">Your Name</h3>
          <p class="lead">Video editor & graphic designer based in <span id="yourCity">Your City</span>. I blend storytelling and design to deliver content that performs — fast turnarounds, consistent quality.</p>
          <ul class="small">
            <li><strong>Tools:</strong> Premiere Pro, After Effects, DaVinci Resolve, Photoshop, Illustrator, Figma</li>
            <li><strong>Industries:</strong> D2C, SaaS, Edu, Events, Creator Economy</li>
            <li><strong>Available:</strong> Freelance • Remote • On-site (contract)</li>
          </ul>
        </div>
        <div>
          <div class="facts">
            <div class="fact"><strong id="kProjects">120+</strong><span class="small">Projects</span></div>
            <div class="fact"><strong id="years">5+</strong><span class="small">Years</span></div>
            <div class="fact"><strong id="happy">90+</strong><span class="small">Happy Clients</span></div>
          </div>
          <div class="card" style="margin-top:14px">
            <h3>Testimonials</h3>
            <div class="grid testimonials">
              <div class="card" style="background:transparent;border-color:rgba(255,255,255,.08)">
                <div style="display:flex;align-items:center">
                  <img class="avatar" src="https://randomuser.me/api/portraits/women/68.jpg" alt="Client avatar"/>
                  <div>
                    <strong>Priya S.</strong>
                    <div class="small">Brand Manager</div>
                  </div>
                </div>
                <p class="quote">“Super fast and the edits were spot on. Our reel CTR doubled.”</p>
              </div>
              <div class="card" style="background:transparent;border-color:rgba(255,255,255,.08)">
                <div style="display:flex;align-items:center">
                  <img class="avatar" src="https://randomuser.me/api/portraits/men/12.jpg" alt="Client avatar"/>
                  <div>
                    <strong>Rohan K.</strong>
                    <div class="small">YouTuber (120k)</div>
                  </div>
                </div>
                <p class="quote">“Clean cuts, punchy pacing, and great sound design. Subscribed!”</p>
              </div>
              <div class="card" style="background:transparent;border-color:rgba(255,255,255,.08)">
                <div style="display:flex;align-items:center">
                  <img class="avatar" src="https://randomuser.me/api/portraits/women/21.jpg" alt="Client avatar"/>
                  <div>
                    <strong>Maria G.</strong>
                    <div class="small">Founder</div>
                  </div>
                </div>
                <p class="quote">“Our new brand kit looks premium across platforms. Highly recommend.”</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact">
      <div class="section-title">
        <h2>Contact</h2>
        <div class="line"></div>
      </div>
      <div class="contact">
        <form id="contactForm" action="https://formspree.io/f/your-id" method="POST">
          <input type="text" name="name" placeholder="Your name" required />
          <input type="email" name="email" placeholder="Your email" required />
          <input type="text" name="subject" placeholder="Project / Subject" />
          <textarea name="message" placeholder="Tell me about your project…" required></textarea>
          <button class="btn btn-primary" type="submit"><i class="fa-solid fa-paper-plane"></i> Send Message</button>
          <div class="small">Prefer email? <a href="mailto:hello@example.com">hello@example.com</a></div>
        </form>
        <div class="card">
          <h3>Let's create something great</h3>
          <p class="lead">Available for freelance projects, retainers, and collaborations. Average response time: <strong>same day</strong>.</p>
          <ul class="small">
            <li><i class="fa-solid fa-location-dot"></i> Based in <span id="cityInline">Your City</span></li>
            <li><i class="fa-brands fa-whatsapp"></i> WhatsApp: <a href="https://wa.me/919999999999" target="_blank">+91 99999 99999</a></li>
            <li><i class="fa-solid fa-link"></i> Links: <a href="#" id="youtube">YouTube</a> • <a href="#" id="instagram">Instagram</a> • <a href="#" id="behance">Behance</a> • <a href="#" id="dribbble">Dribbble</a></li>
          </ul>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div>© <span id="year"></span> <span id="footerName">Your Name</span>. All rights reserved.</div>
    <div class="social">
      <a href="#" aria-label="YouTube"><i class="fa-brands fa-youtube"></i></a>
      <a href="#" aria-label="Instagram"><i class="fa-brands fa-instagram"></i></a>
      <a href="#" aria-label="Behance"><i class="fa-brands fa-behance"></i></a>
      <a href="#" aria-label="Dribbble"><i class="fa-brands fa-dribbble"></i></a>
    </div>
  </footer>

  <!-- Lightbox Modal -->
  <dialog id="lightbox" style="border:none;border-radius:20px;max-width:min(1000px,96vw);width:100%;padding:0;background:#0b0f15">
    <button id="closeLightbox" class="btn" style="position:absolute;right:12px;top:12px;z-index:2"><i class="fa-solid fa-xmark"></i> Close</button>
    <div id="lightboxContent"></div>
  </dialog>

  <script>
    // Basic personalization variables (edit once here)
    const SITE = {
      name: "Your Name",
      city: "Your City",
      resumeUrl: "#", // e.g. link to Google Drive PDF
      youtube: "https://youtube.com/",
      instagram: "https://instagram.com/",
      behance: "https://behance.net/",
      dribbble: "https://dribbble.com/",
      whatsapp: "https://wa.me/919999999999"
    };

    // Populate dynamic text/links
    document.getElementById('year').textContent = new Date().getFullYear();
    ['brandName','yourName','footerName'].forEach(id=>document.getElementById(id).textContent = SITE.name);
    document.getElementById('yourCity').textContent = SITE.city;
    document.getElementById('cityInline').textContent = SITE.city;
    document.getElementById('resumeLink').href = SITE.resumeUrl;
    document.getElementById('youtube').href = SITE.youtube;
    document.getElementById('instagram').href = SITE.instagram;
    document.getElementById('behance').href = SITE.behance;
    document.getElementById('dribbble').href = SITE.dribbble;
    document.querySelector('a[href^="https://wa.me/"]').href = SITE.whatsapp;

    // Portfolio filters
    const filters = document.querySelectorAll('.filter');
    const tiles = document.querySelectorAll('.tile');
    filters.forEach(f=>f.addEventListener('click',()=>{
      filters.forEach(x=>x.classList.remove('active'));
      f.classList.add('active');
      const t = f.dataset.filter;
      tiles.forEach(card=>{
        card.style.display = (t==='all' || card.dataset.type===t) ? 'block' : 'none';
      });
    }));

    // Lightbox for tiles
    const dialog = document.getElementById('lightbox');
    const box = document.getElementById('lightboxContent');
    const closeBtn = document.getElementById('closeLightbox');
    const openLightbox = (el)=>{
      box.innerHTML = '';
      const clone = el.querySelector('video, img').cloneNode(true);
      clone.removeAttribute('muted');
      if(clone.tagName==='VIDEO'){ clone.controls = true; clone.autoplay = true; clone.loop = true; }
      clone.style.width = '100%';
      clone.style.height = 'auto';
      box.appendChild(clone);
      dialog.showModal();
    }
    tiles.forEach(t=>{
      t.addEventListener('click',()=>openLightbox(t));
      t.addEventListener('keypress',(e)=>{ if(e.key==='Enter') openLightbox(t) });
    });
    closeBtn.addEventListener('click',()=>dialog.close());

    // Accessible ESC close
    document.addEventListener('keydown',e=>{ if(e.key==='Escape' && dialog.open) dialog.close() });
  </script>

  <!-- SEO Schema -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Person",
    "name": "Your Name",
    "jobTitle": "Video Editor & Graphic Designer",
    "url": "https://your-domain.com",
    "sameAs": [
      "https://instagram.com/yourhandle",
      "https://behance.net/yourhandle",
      "https://dribbble.com/yourhandle",
      "https://youtube.com/@yourhandle"
    ]
  }
  </script>
</body>
</html>
