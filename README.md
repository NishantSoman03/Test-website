<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Tantronics Industries LLP – Electronics • Automation • Embedded Systems • Power Electronics • Medicare</title>
  <meta name="description" content="Tantronics Industries LLP delivers innovative electronics: embedded systems, power electronics, IoT and custom R&D-driven products for industry." />
  <meta name="theme-color" content="#181818" />

  <!-- Fonts & Icons -->
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
  <link rel="icon" type="image/png" href="./static/Tantronics Logo.png">

  <style>
    :root{
      --bg:#0f1115; --fg:#e7e9ee; --muted:#aeb4c0; --brand:#41d1b7; --card:#171a20; --stroke:#23262d;
      --pill:#1f2330; --accent:#2a2f3d;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0;font-family:Inter,system-ui,Segoe UI,Roboto,Helvetica,Arial,sans-serif;background:var(--bg);color:var(--fg);}

    /* LAYOUT uses percentages / vw / vh */
    section{padding:6vh 4vw}
    .container{width:92vw; margin:0 auto}
    .section-head{margin-bottom:3vh}
    .section-head h2{font-size:clamp(1.25rem,2.2vw,2rem); margin:0 0 1vh 0}
    .lead{color:var(--muted)}

    /* HEADER */
    header{position:sticky; top:0; z-index:10; background:rgba(15,17,21,.75); backdrop-filter:saturate(140%) blur(10px); border-bottom:1px solid var(--stroke)}
    .nav{width:92vw; margin:0 auto; display:flex; align-items:center; justify-content:space-between; padding:1.5vh 0}
    .brand{display:flex; align-items:center; gap:1vw; text-decoration:none; color:var(--fg)}
    .brand .header-logo{height:4.5vh; width:auto}
    nav ul{list-style:none; display:flex; gap:2vw; margin:0; padding:0}
    nav a{color:var(--fg); text-decoration:none; font-weight:500}
    .nav-cta{padding:.8vh 1.6vw; border:1px solid var(--stroke); border-radius:999px}
    .hamburger{display:none; background:none; color:var(--fg); border:0; font-size:1.25rem}

    /* MOBILE MENU (percentage width) */
    #mobileMenu{display:none; position:absolute; left:0; top:100%; width:100vw; background:var(--card); border-top:1px solid var(--stroke)}
    #mobileMenu a{display:block; padding:2.5vh 4vw}

    /* HERO */
    .hero{min-height:70vh; display:grid; place-items:center; text-align:center; background:radial-gradient(60% 80% at 50% 0%, #182030 0%, transparent 70%)}
    .hero-inner{width:80vw; max-width:100%; margin:0 auto}
    .hero .eyebrow{display:inline-block; padding:.6vh 1vw; border:1px solid var(--stroke); border-radius:999px; color:var(--muted); margin-bottom:2vh}
    .hero h1{font-size:clamp(1.75rem,4vw,3rem); margin:1vh 0 2vh}
    .cta-row{display:flex; gap:2vw; justify-content:center; flex-wrap:wrap}

    /* BUTTONS */
    .btn{display:inline-flex; align-items:center; gap:.6vw; padding:1.2vh 1.6vw; border-radius:12px; border:1px solid var(--stroke); text-decoration:none; color:var(--fg)}
    .btn-primary{background:linear-gradient(180deg, #49e7cb, #34b39c); color:#071b17; border:0}
    .btn-ghost{background:transparent}

    /* ABOUT */
    .about-grid{display:grid; grid-template-columns:100%; gap:4vw}
    @media (min-width: 900px){
      .about-grid{grid-template-columns: 60% 38%; gap:2%}
    }
    .about-card{background:var(--card); border:1px solid var(--stroke); border-radius:16px; padding:3vh 3vw}
    .kpis{display:grid; grid-template-columns: repeat(2, 48%); gap:4%; margin-top:2.5vh}
    @media (min-width: 900px){.kpis{grid-template-columns: repeat(4, 23%); gap:3%}}
    .kpi h3{margin:.2rem 0; color:var(--brand)}

    /* PRODUCTS */
    .product-grid{display:grid; grid-template-columns:100%; gap:4vw}
    @media (min-width: 700px){
      .product-grid{grid-template-columns: 48% 48%; gap:4%}
    }
    @media (min-width: 1100px){
      .product-grid{grid-template-columns: 32% 32% 32%; gap:2%}
    }
    .card{background:var(--card); border:1px solid var(--stroke); border-radius:16px; overflow:hidden}
    .card .p{padding:2.8vh 2.8vw}
    .pill{display:inline-block; background:var(--pill); border:1px solid var(--stroke); padding:.6vh 1vw; border-radius:999px; margin-bottom:1.2vh; color:var(--muted)}
    .features{display:flex; flex-wrap:wrap; gap:1vw; margin-top:1.8vh}
    .features span{padding:.5vh 1vw; border:1px solid var(--stroke); border-radius:999px; color:var(--muted)}

    /* CAROUSELS – percentage sizing */
    .carousel{position:relative; width:100%; /* height is derived from width via padding (percentage) */}
    .ratio-4x3{height:0; padding-top:75%} /* 4:3 via percentage of width */
    .carousel img{position:absolute; inset:0; width:100%; height:100%; object-fit:cover; display:none}
    .carousel img.active{display:block}
    .carousel button{position:absolute; top:50%; transform:translateY(-50%); width:6vh; height:6vh; border-radius:50%; border:0; background:rgba(0,0,0,.35); color:#fff; cursor:pointer}
    .carousel .prev{left:2%}
    .carousel .next{right:2%}

    /* CTA */
    .panel{display:flex; gap:3vw; align-items:center; justify-content:space-between; background:linear-gradient(180deg,#151925,#0f121a); border:1px solid var(--stroke); border-radius:20px; padding:3vh 3vw}
    .panel .lead{max-width:70%}

    /* CONTACT */
    .contact-grid{display:grid; grid-template-columns:100%; gap:4vw}
    @media (min-width: 900px){
      .contact-grid{grid-template-columns: 58% 40%; gap:2%}
    }
    form{display:grid; grid-template-columns:48% 48%; gap:4%; background:var(--card); border:1px solid var(--stroke); border-radius:16px; padding:3vh 3vw}
    form .full{grid-column:1 / -1}
    label{display:block; margin:0 0 .8vh}
    input,select,textarea{width:100%; padding:1.2vh 1vw; background:#0e1016; border:1px solid var(--stroke); border-radius:12px; color:var(--fg)}
    textarea{min-height:18vh; resize:vertical}
    .form-note{color:var(--muted)}

    /* FOOTER */
    footer{border-top:1px solid var(--stroke)}
    .foot{width:92vw; margin:0 auto; display:grid; grid-template-columns:100%; gap:4vw; padding:5vh 0}
    @media (min-width: 900px){.foot{grid-template-columns: 48% 24% 24%; gap:2%}}
    .sub{border-top:1px solid var(--stroke); padding:2vh 4vw; color:var(--muted); text-align:center}

    /* UTIL */
    img{max-width:100%; height:auto; display:block}
  </style>
</head>
<body>
  <!-- Header -->
  <header>
    <div class="nav">
      <a class="brand" href="#home" aria-label="Tantronics home">
        <img src="./static/Tantronics Logo.png" alt="Tantronics Logo" class="header-logo" loading="lazy">
        <span>Tantronics Industries LLP</span>
      </a>
      <nav aria-label="Primary">
        <button class="hamburger" aria-label="Toggle menu"><i class="fa-solid fa-bars"></i></button>
        <ul class="desktop">
          <li><a href="#about">About</a></li>
          <li><a href="#products">Products</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a class="nav-cta" href="#enquiry">Get a Quote</a></li>
        </ul>
        <div id="mobileMenu">
          <a href="#about">About</a>
          <a href="#products">Products</a>
          <a href="#contact">Contact</a>
          <a href="#enquiry">Get a Quote</a>
        </div>
      </nav>
    </div>
  </header>

  <!-- Hero -->
  <section class="hero" id="home" role="banner" aria-label="Hero">
    <div class="hero-inner">
      <span class="eyebrow">Electronics • Automation • Embedded Systems • Power Electronics • Medicare</span>
      <h1>Industrial Automation Solutions</h1>
      <p class="lead">From water level controllers and float sensors to custom embedded hardware and IoT systems, we build reliable, cost‑effective products engineered for Indian conditions.</p>
      <div class="cta-row">
        <a href="#products" class="btn btn-primary"><i class="fa-solid fa-store"></i> Explore Products</a>
        <a href="#contact" class="btn btn-ghost"><i class="fa-solid fa-envelope"></i> Contact Us</a>
      </div>
    </div>
  </section>

  <!-- About -->
  <section class="about" id="about">
    <div class="container about-grid">
      <div class="about-copy">
        <div class="section-head">
          <h2>About Tantronics</h2>
          <p class="lead">Tantronics Industries LLP is a technology-driven company dedicated to delivering innovative solutions across the entire spectrum of electronics. Our expertise spans embedded systems, power electronics, research & development, and advanced electronic product design, enabling us to serve diverse industries with cutting-edge, reliable, and cost-effective technologies.<br><br>
          We specialize in developing embedded hardware and software solutions, IoT-based systems, industrial automation, and customized electronic products tailored to client needs. With a strong foundation in power electronics and energy-efficient designs, we contribute to smarter, sustainable technologies for the future.<br><br>
          Our Research & Development division is committed to exploring the latest trends in artificial intelligence, machine learning, robotics, automotive electronics, consumer electronics, and defense technologies, ensuring that we remain at the forefront of technological innovation. At Tantronics, we aim to be a one-stop destination for electronics innovation, empowering industries by providing end-to-end solutions from concept, prototyping, and product design, to manufacturing and deployment.</p>
        </div>
        <div class="about-card">
          <h3 style="margin-top:0; color:var(--brand)">What we do</h3>
          <ul>
            <li>Design & manufacture of <strong>water level controllers</strong>, <strong>float switches</strong>, and <strong>sensor modules</strong>.</li>
            <li>Custom <strong>embedded hardware & firmware</strong> for OEMs.</li>
            <li><strong>IoT & industrial automation</strong> with dashboards and alerts.</li>
            <li><strong>R&D & prototyping</strong> for new product development.</li>
          </ul>
          <div class="kpis" aria-label="Key stats">
            <div class="kpi">
              <h3>10K+</h3>
              <div>Units deployed</div>
            </div>
            <div class="kpi">
              <h3>25+</h3>
              <div>SKUs & variants</div>
            </div>
            <div class="kpi">
              <h3>4+ yrs</h3>
              <div>Engineering Team</div>
            </div>
            <div class="kpi">
              <h3>Pan‑India</h3>
              <div>Service & Shipping</div>
            </div>
          </div>
        </div>
      </div>
      <aside>
        <img src="./static/Tantronics Logo.png" alt="Tantronics Logo" loading="lazy" style="border-radius:16px; border:1px solid var(--stroke); background:#232323; padding:1rem;">
        <div class="form-note" style="margin-top:.75rem"></div>
      </aside>
    </div>
  </section>

  <!-- Products -->
  <section class="products" id="products">
    <div class="container">
      <div class="section-head">
        <h2>Featured Products</h2>
      </div>
      <div class="product-grid">
        <!-- Card 1 -->
        <article class="card">
          <div class="carousel ratio-4x3" data-group="wlc">
            <img src="./static/wi1.jpg" alt="Water Level Controller 1" class="active">
            <img src="./static/wi2.jpg" alt="Water Level Controller 2">
            <img src="./static/wi3.jpg" alt="Water Level Controller 3">
            <img src="./static/wi4.jpg" alt="Water Level Controller 4">
            <button class="prev" aria-label="Previous">&#8592;</button>
            <button class="next" aria-label="Next">&#8594;</button>
          </div>
          <div class="p">
            <span class="pill">Controller</span>
            <h3>Automatic Water Level Controller in Collaboration with WATCO Industries</h3>
            <p>Auto start/stop for pumps, dry‑run protection, and manual override. Supports overhead/underground tanks.</p>
            <ul style="margin:0 0 0 1em; padding:0; color:inherit;">
              <li>LDS</li>
              <li>Float Sensor</li>
              <li>MPWL</li>
              <li>Liquid Level Controller</li>
            </ul>
            <div class="features">
              <span>230V AC</span>
              <span>Dry‑run Safe</span>
              <span>LED Status</span>
            </div>
          </div>
        </article>

        <!-- Card 2 -->
        <article class="card">
          <img src="./static/solar panel cleaner robot.jpg" alt="Solar Panel Cleaning Robot" loading="lazy">
          <div class="p">
            <span class="pill">Robotics</span>
            <h3>Solar Panel Cleaning Robot</h3>
            <p>A wirelessly operated solar panel cleaning robot is an autonomous system that uses remote control or IoT connectivity to efficiently clean dust and debris from solar panels, ensuring maximum energy output without manual intervention.</p>
            <div class="features">
              <span>2.4 GHz Wi‑Fi/ Bluetooth LE 5.0.</span>
              <span>Emergency Stop (E‑Stop) with NC contact</span>
            </div>
          </div>
        </article>

        <!-- Card 3 -->
        <article class="card">
          <img src="./static/Digital-Timer.jpg" alt="Light dependent switch module" loading="lazy">
          <div class="p">
            <span class="pill">Industrial Control Equipment</span>
            <h3>Microcontroller Based Programmable Timer</h3>
            <p>A microcontroller-based programmable timer is an electronic device that uses a microcontroller to schedule and control switching operations of connected loads with user-defined ON/OFF times, ensuring precision and automation.</p>
            <div class="features">
              <span>12–24V</span>
              <span>RTC with backup</span>
              <span>EEPROM/Flash storage</span>
            </div>
          </div>
        </article>

        <!-- Card 4 -->
        <article class="card">
          <div class="carousel ratio-4x3" data-group="auto">
            <img src="./static/pt1.1.JPG" alt="Automobile Alert Unit 1" class="active">
            <img src="./static/pt1.JPG" alt="Automobile Alert Unit 2">
            <button class="prev" aria-label="Previous">&#8592;</button>
            <button class="next" aria-label="Next">&#8594;</button>
          </div>
          <div class="p">
            <span class="pill">Automobile</span>
            <h3>AN INDICATION ALERT UNIT SYSTEM FOR AUTOMOBILE DRIVING LIGHTS</h3>
            <p>Unit System for Automobile Driving Lights is an innovative patented solution designed to monitor, detect, and alert drivers of High Beam vehicle lighting, ensuring enhanced road safety and compliance.</p>
            <div class="features">
              <span>12V/24V DC</span>
              <span>Vibration/Shock resistance</span>
              <span>Failsafe NC contacts</span>
            </div>
          </div>
        </article>

        <!-- Card 5 -->
        <article class="card">
          <div class="carousel ratio-4x3" data-group="smps">
            <img src="./static/ps.jpg" alt="Industrial SMPS power supply 1" class="active">
            <img src="./static/ps1.jpg" alt="Industrial SMPS power supply 2">
            <img src="./static/ps2.jpg" alt="Industrial SMPS power supply 3">
            <button class="prev" aria-label="Previous">&#8592;</button>
            <button class="next" aria-label="Next">&#8594;</button>
          </div>
          <div class="p">
            <span class="pill">Power</span>
            <h3>Industrial SMPS (12V/24V)</h3>
            <p>High‑efficiency compact power supplies with protections and low ripple for sensitive control electronics.</p>
            <div class="features">
              <span>85–265VAC</span>
              <span>OVP/OCP</span>
              <span>CE</span>
            </div>
          </div>
        </article>

        <!-- Card 6 -->
        <article class="card">
          <img src="./static/ozone.jpg" alt="Custom PCB and enclosure mockup" loading="lazy">
          <div class="p">
            <span class="pill">OEM</span>
            <h3>Custom OEM Development</h3>
            <p>End‑to‑end design: schematics, PCB, firmware, enclosure and testing. NDA‑friendly engagement.</p>
            <div class="features">
              <span>Rapid Proto</span>
              <span>DFM/DFA</span>
              <span>ISO Docs</span>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>

  <!-- CTA Banner -->
  <section class="cta" id="enquiry" aria-label="Enquiry">
    <div class="container">
      <div class="panel">
        <div>
          <h2 style="margin:.2rem 0; color:var(--brand)">Need help selecting the right solution?</h2>
          <div class="lead">Tell us your application, power requirements, and connectivity preferences—we’ll recommend the perfect electronics, embedded, or automation system for you.</div>
        </div>
        <a href="#contact" class="btn btn-primary"><i class="fa-solid fa-comment-dots"></i> Talk to Sales</a>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section class="contact" id="contact">
    <div class="container">
      <div class="section-head">
        <h2>Contact & Enquiry</h2>
        <p class="lead">Fill the form and our team will get back within 1/2 business days.</p>
      </div>
      <div class="contact-grid">
        <form id="contactForm" action="#" method="POST" novalidate>
          <div>
            <label for="name">Name</label>
            <input type="text" id="name" name="name" placeholder="Your name" required>
          </div>
          <div>
            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="you@example.com" required>
          </div>
          <div>
            <label for="phone">Phone</label>
            <input type="tel" id="phone" name="phone" placeholder="+91‑XXXXXXXXXX">
          </div>
          <div>
            <label for="product">Interested In</label>
            <select id="product" name="product">
              <option>Automatic Water Level Controller in Collaboration with WATCO Industries</option>
              <option>Float Sensor</option>
              <option>MPWL</option>
              <option>Liquid Level Controller</option>
              <option>Solar Panel Cleaning Robot</option>
              <option>Microcontroller Based Programmable Timer</option>
              <option>Pump Controller IoT</option>
              <option>Industrial SMPS</option>
              <option>Custom OEM</option>
            </select>
          </div>
          <div class="full">
            <label for="message">Message</label>
            <textarea id="message" name="message" placeholder="Share your Requirement Details" required></textarea>
          </div>
          <div class="full" style="display:flex; align-items:center;">
            <label class="form-note" style="display:flex; align-items:center; font-weight:400; white-space:nowrap; margin-left:0;">
              <input type="checkbox" id="consent" required style="margin-right:4px;"> I agree to be contacted about my enquiry.
            </label>
          </div>
          <div class="full">
            <button class="btn btn-primary" type="submit"><i class="fa-solid fa-paper-plane"></i> Send Enquiry</button>
          </div>
          <p id="formStatus" class="form-note full" role="status" aria-live="polite"></p>
        </form>
        <aside>
          <div class="about-card" style="height:100%">
            <h3 style="margin-top:0; color:var(--brand)">Office</h3>
            <p>
              Mihir Bidwai<br>
              Founder & Director / Electronics Engineer<br>
              <a href="tel:+917820912136"><i class="fa-solid fa-phone"></i> +91 7820912136</a><br>
              <a href="mailto:tantronicsindustries@gmail.com"><i class="fa-solid fa-envelope"></i> tantronicsindustries@gmail.com</a><br>
              Warje, Pune, Maharashtra 411058<br><br>
              <strong>Opening Hours:</strong> 10:00AM - 6:00PM
            </p>
            <div style="aspect-ratio: 4/3; overflow:hidden; border-radius:12px; border:1px solid #e2e8f0; margin-top:1rem;">
              <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3784.154432274673!2d73.79742399999999!3d18.476662700000002!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bc2950ca7c99333%3A0xc91c6645095e74cc!2sTantronics%20Industries!5e0!3m2!1sen!2sin!4v1755714398449!5m2!1sen!2sin" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
            <p class="form-note" style="margin-top:.75rem">Update your address, phone and map link. Add GSTIN, CIN, support timings if needed.</p>
          </div>
        </aside>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="foot">
      <div>
        <h4>Tantronics Industries LLP</h4>
        <p>Specialists in Electronics, Embedded Systems, Power Electronics & R&D. We design and manufacture practical automation that just works.</p>
      </div>
      <div>
        <h4>Quick Links</h4>
        <p><a href="#about">About</a><br>
           <a href="#products">Products</a><br>
           <a href="#contact">Contact</a></p>
      </div>
      <div>
        <h4>Follow</h4>
        <p>
          <a href="#" aria-label="LinkedIn"><i class="fa-brands fa-linkedin"></i> LinkedIn</a><br>
          <a href="#" aria-label="Instagram"><i class="fa-brands fa-instagram"></i> Instagram</a><br>
          <a href="#" aria-label="YouTube"><i class="fa-brands fa-youtube"></i> YouTube</a>
        </p>
      </div>
    </div>
    <div class="sub">
      <div>© <span id="year"></span> Tantronics Industries LLP. All rights reserved.</div>
      <div style="margin-top:.25rem; font-size:.85rem">Designed & Developed by <a href="#">Tantronics Industries LLP</a></div>
    </div>
  </footer>

  <script>
    // Mobile menu toggle (menu is full-width %)
    const burger = document.querySelector('.hamburger');
    const mobileMenu = document.getElementById('mobileMenu');
    burger?.addEventListener('click', () => {
      const isOpen = mobileMenu.style.display === 'block';
      mobileMenu.style.display = isOpen ? 'none' : 'block';
    });
    mobileMenu?.querySelectorAll('a').forEach(a => a.addEventListener('click', ()=>{ mobileMenu.style.display = 'none'; }));

    // Year in footer
    document.getElementById('year').textContent = new Date().getFullYear();

    // Basic form validation + submission UX
    const form = document.getElementById('contactForm');
    const statusEl = document.getElementById('formStatus');
    form?.addEventListener('submit', async (e) => {
      e.preventDefault();
      statusEl.textContent = '';
      if(!form.checkValidity()){
        statusEl.textContent = 'Please fill required fields.';
        return;
      }
      statusEl.textContent = 'Thanks! Your enquiry has been sent.';
      form.reset();
    });

    // Generic % carousel (works for all groups)
    function initCarousel(root){
      const imgs = Array.from(root.querySelectorAll('img'));
      const prev = root.querySelector('.prev');
      const next = root.querySelector('.next');
      let idx = 0;
      function show(i){ imgs.forEach((im,n)=> im.classList.toggle('active', n===i)); }
      prev?.addEventListener('click', ()=>{ idx = (idx - 1 + imgs.length) % imgs.length; show(idx); });
      next?.addEventListener('click', ()=>{ idx = (idx + 1) % imgs.length; show(idx); });
      show(idx);
    }
    document.querySelectorAll('.carousel').forEach(initCarousel);
  </script>
</body>
</html>
