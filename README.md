<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI Micro-Tool | Free AI Tools for Content Creators - Title, Bio & Hashtag Generator</title>
  <meta name="description" content="AI Micro-Tool provides fast, free AI-powered tools for content creators: YouTube Video Title Generator, Instagram Bio Generator, and Hashtag Generator. Create better content in seconds.">
  <meta name="keywords" content="AI title generator, bio generator, hashtag generator, YouTube titles, Instagram bio, content creator tools, free AI tools, micro tools">
  <meta name="author" content="AI Micro-Tool">
  <meta name="robots" content="index, follow">
  <link rel="canonical" href="https://aimicrotool.example.com/">
  <meta property="og:title" content="AI Micro-Tool | Free AI Tools for Content Creators">
  <meta property="og:description" content="Generate video titles, bios and hashtags instantly with our free AI micro-tools.">
  <meta property="og:type" content="website">
  <meta property="og:image" content="robot.png">
  <meta name="twitter:card" content="summary">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
      background-color: #ffffff;
      color: #000000;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      line-height: 1.5;
    }

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 24px 40px;
      max-width: 1100px;
      width: 100%;
      margin: 0 auto;
    }

    .logo {
      display: flex;
      flex-direction: column;
      font-weight: 700;
      font-size: 2.2rem;
      line-height: 1.15;
      letter-spacing: -0.5px;
    }

    .logo span {
      display: block;
    }

    .header-img {
      width: 140px;
      height: 140px;
      object-fit: contain;
    }

    main {
      flex: 1;
      max-width: 700px;
      width: 100%;
      margin: 0 auto;
      padding: 20px 24px 60px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .tools-container {
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0;
    }

    .tool-btn {
      width: 100%;
      max-width: 420px;
      height: 72px;
      margin-bottom: 72px;
      background-color: #ffffff;
      border: 2px solid #000000;
      border-radius: 16px;
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
      font-size: 1.25rem;
      color: #000000;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      display: flex;
      align-items: center;
      justify-content: center;
      outline: none;
    }

    .tool-btn:last-of-type {
      margin-bottom: 0;
    }

    .tool-btn:hover {
      background-color: #f8f8f8;
      transform: translateY(-2px);
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    }

    .tool-btn:active {
      transform: translateY(0);
    }

    .tool-btn.active {
      background-color: #000000;
      color: #ffffff;
    }

    .tool-panel {
      width: 100%;
      max-width: 520px;
      max-height: 0;
      overflow: hidden;
      opacity: 0;
      transition: max-height 0.45s cubic-bezier(0.4, 0, 0.2, 1),
                  opacity 0.35s ease,
                  margin 0.35s ease;
      margin: 0 auto;
    }

    .tool-panel.open {
      max-height: 700px;
      opacity: 1;
      margin-top: -40px;
      margin-bottom: 48px;
    }

    .panel-inner {
      padding: 8px 0 16px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
    }

    .input-area {
      width: 100%;
      aspect-ratio: 16 / 9;
      min-height: 160px;
      max-height: 280px;
      border: 2px solid #000000;
      border-radius: 12px;
      padding: 18px;
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
      font-size: 1rem;
      color: #000000;
      resize: vertical;
      outline: none;
      background: #ffffff;
      transition: border-color 0.25s ease;
    }

    .input-area::placeholder {
      color: rgba(0, 0, 0, 0.35);
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
    }

    .input-area:focus {
      border-color: #333;
    }

    .generate-btn {
      width: 200px;
      height: 52px;
      background-color: #ffffff;
      border: 2px solid #000000;
      border-radius: 14px;
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
      font-size: 1.1rem;
      color: #000000;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      outline: none;
    }

    .generate-btn:hover {
      background-color: #000000;
      color: #ffffff;
      transform: translateY(-2px);
    }

    .generate-btn:active {
      transform: translateY(0);
    }

    .generate-btn:disabled {
      opacity: 0.5;
      cursor: not-allowed;
      transform: none;
    }

    .result-box {
      width: 100%;
      min-height: 0;
      max-height: 0;
      overflow: hidden;
      opacity: 0;
      border: 2px solid #000000;
      border-radius: 12px;
      padding: 0 18px;
      font-family: 'Roboto', sans-serif;
      font-size: 1rem;
      line-height: 1.6;
      background: #fafafa;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      white-space: pre-wrap;
    }

    .result-box.show {
      min-height: 80px;
      max-height: 300px;
      opacity: 1;
      padding: 16px 18px;
      overflow-y: auto;
    }

    footer {
      border-top: 1px solid #e5e5e5;
      padding: 28px 24px;
      text-align: center;
    }

    .footer-links {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 28px;
    }

    .footer-links a {
      font-family: 'Roboto', sans-serif;
      font-weight: 400;
      font-size: 0.95rem;
      color: #000000;
      text-decoration: none;
      position: relative;
      transition: color 0.25s ease;
      cursor: pointer;
    }

    .footer-links a::after {
      content: '';
      position: absolute;
      bottom: -3px;
      left: 0;
      width: 0;
      height: 1px;
      background: #000;
      transition: width 0.25s ease;
    }

    .footer-links a:hover::after {
      width: 100%;
    }

    .footer-links a:hover {
      color: #333;
    }

    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0, 0, 0, 0.4);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 1000;
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.3s ease, visibility 0.3s ease;
      padding: 20px;
    }

    .modal-overlay.open {
      opacity: 1;
      visibility: visible;
    }

    .modal {
      background: #ffffff;
      border: 2px solid #000000;
      border-radius: 16px;
      width: 100%;
      max-width: 560px;
      max-height: 85vh;
      overflow-y: auto;
      padding: 32px 28px 28px;
      position: relative;
      transform: translateY(30px) scale(0.97);
      transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .modal-overlay.open .modal {
      transform: translateY(0) scale(1);
    }

    .modal-close {
      position: absolute;
      top: 14px;
      right: 14px;
      width: 36px;
      height: 36px;
      border: 2px solid #000000;
      border-radius: 50%;
      background: #ffffff;
      font-size: 1.2rem;
      line-height: 1;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.25s ease;
      font-family: 'Roboto', sans-serif;
    }

    .modal-close:hover {
      background: #000000;
      color: #ffffff;
    }

    .modal h2 {
      font-weight: 700;
      font-size: 1.5rem;
      margin-bottom: 18px;
      padding-right: 40px;
    }

    .modal p {
      margin-bottom: 14px;
      font-size: 0.98rem;
    }

    .modal h3 {
      font-weight: 700;
      font-size: 1.1rem;
      margin: 20px 0 10px;
    }

    .contact-form {
      display: flex;
      flex-direction: column;
      gap: 16px;
      width: 100%;
    }

    .contact-form label {
      font-size: 0.9rem;
      font-weight: 400;
      display: block;
      margin-bottom: 4px;
    }

    .contact-form input,
    .contact-form textarea {
      width: 100%;
      border: 2px solid #000000;
      border-radius: 10px;
      padding: 12px 14px;
      font-family: 'Roboto', sans-serif;
      font-size: 1rem;
      outline: none;
      background: #fff;
    }

    .contact-form textarea {
      aspect-ratio: 16 / 9;
      min-height: 120px;
      resize: vertical;
    }

    .contact-form input:focus,
    .contact-form textarea:focus {
      border-color: #333;
    }

    .send-btn {
      width: 180px;
      height: 48px;
      align-self: center;
      background: #ffffff;
      border: 2px solid #000000;
      border-radius: 14px;
      font-family: 'Roboto', sans-serif;
      font-size: 1.05rem;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 8px;
    }

    .send-btn:hover {
      background: #000;
      color: #fff;
    }

    .spinner {
      display: inline-block;
      width: 18px;
      height: 18px;
      border: 2px solid #ccc;
      border-top-color: #000;
      border-radius: 50%;
      animation: spin 0.7s linear infinite;
      vertical-align: middle;
      margin-right: 8px;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    @media (max-width: 600px) {
      header {
        padding: 18px 20px;
      }
      .logo {
        font-size: 1.7rem;
      }
      .header-img {
        width: 100px;
        height: 100px;
      }
      .tool-btn {
        height: 64px;
        margin-bottom: 64px;
        font-size: 1.1rem;
      }
      main {
        padding: 12px 16px 40px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo" aria-label="AI Micro-Tool">
      <span>AI</span>
      <span>Micro</span>
      <span>Tool</span>
    </div>
    <img src="robot.png" alt="Friendly AI robot mascot" class="header-img" width="140" height="140">
  </header>

  <main>
    <div class="tools-container">
      <button class="tool-btn" data-tool="title" aria-expanded="false">Video Title Generator</button>
      <div class="tool-panel" id="panel-title" role="region">
        <div class="panel-inner">
          <textarea class="input-area" id="input-title" placeholder="About your video" aria-label="Describe your video"></textarea>
          <button class="generate-btn" data-generate="title">Generate</button>
          <div class="result-box" id="result-title" aria-live="polite"></div>
        </div>
      </div>

      <button class="tool-btn" data-tool="bio" aria-expanded="false">Bio Generator</button>
      <div class="tool-panel" id="panel-bio" role="region">
        <div class="panel-inner">
          <textarea class="input-area" id="input-bio" placeholder="About yourself" aria-label="Describe yourself"></textarea>
          <button class="generate-btn" data-generate="bio">Generate</button>
          <div class="result-box" id="result-bio" aria-live="polite"></div>
        </div>
      </div>

      <button class="tool-btn" data-tool="hashtag" aria-expanded="false">Hashtag Generator</button>
      <div class="tool-panel" id="panel-hashtag" role="region">
        <div class="panel-inner">
          <textarea class="input-area" id="input-hashtag" placeholder="About your content" aria-label="Describe your content"></textarea>
          <button class="generate-btn" data-generate="hashtag">Generate</button>
          <div class="result-box" id="result-hashtag" aria-live="polite"></div>
        </div>
      </div>
    </div>
  </main>

  <footer>
    <nav class="footer-links" aria-label="Footer navigation">
      <a data-modal="about">About Us</a>
      <a data-modal="contact">Contact Us</a>
      <a data-modal="privacy">Privacy Policy</a>
      <a data-modal="terms">Terms & Conditions</a>
    </nav>
  </footer>

  <div class="modal-overlay" id="modal-overlay" role="dialog" aria-modal="true">
    <div class="modal" id="modal-content">
      <button class="modal-close" aria-label="Close">&times;</button>
      <div id="modal-body"></div>
    </div>
  </div>

  <script>
    const toolBtns = document.querySelectorAll('.tool-btn');
    const panels = {
      title: document.getElementById('panel-title'),
      bio: document.getElementById('panel-bio'),
      hashtag: document.getElementById('panel-hashtag')
    };
    let openTool = null;

    toolBtns.forEach(btn => {
      btn.addEventListener('click', () => {
        const tool = btn.dataset.tool;
        if (openTool === tool) {
          panels[tool].classList.remove('open');
          btn.classList.remove('active');
          btn.setAttribute('aria-expanded', 'false');
          openTool = null;
        } else {
          if (openTool) {
            panels[openTool].classList.remove('open');
            document.querySelector('.tool-btn[data-tool="' + openTool + '"]').classList.remove('active');
            document.querySelector('.tool-btn[data-tool="' + openTool + '"]').setAttribute('aria-expanded', 'false');
          }
          panels[tool].classList.add('open');
          btn.classList.add('active');
          btn.setAttribute('aria-expanded', 'true');
          openTool = tool;
        }
      });
    });

    function generateTitle(text) {
      const ideas = [
        '🔥 ' + text.slice(0, 40) + '... You Won\'t Believe What Happens Next!',
        'How to Master ' + text.slice(0, 30) + ' in 2026 (Step-by-Step Guide)',
        'The Ultimate Guide to ' + text.slice(0, 35) + ' – Everything You Need',
        text.slice(0, 25) + ' Secrets That Changed Everything',
        'Why ' + text.slice(0, 30) + ' is the Future of Content Creation'
      ];
      return ideas[Math.floor(Math.random() * ideas.length)];
    }

    function generateBio(text) {
      return '✨ ' + text + '\n\n🚀 Helping creators grow with smart tools & tips\n📌 Free resources every week\n👇 Let\'s connect & create together';
    }

    function generateHashtags(text) {
      const words = text.toLowerCase().replace(/[^a-z0-9\s]/g, '').split(/\s+/).filter(function(w) { return w.length > 2; });
      const base = words.slice(0, 5).map(function(w) { return '#' + w; });
      const extras = ['#ContentCreator', '#Viral', '#Growth', '#AITools', '#CreatorEconomy', '#SocialMediaTips', '#Reels', '#YouTubeTips'];
      return Array.from(new Set(base.concat(extras))).slice(0, 12).join(' ');
    }

    document.querySelectorAll('.generate-btn').forEach(function(btn) {
      btn.addEventListener('click', async function() {
        const type = btn.dataset.generate;
        const input = document.getElementById('input-' + type);
        const result = document.getElementById('result-' + type);
        const text = input.value.trim();

        if (!text) {
          result.textContent = 'Please write something first.';
          result.classList.add('show');
          return;
        }

        btn.disabled = true;
        const original = btn.innerHTML;
        btn.innerHTML = '<span class="spinner"></span>Generating...';

        await new Promise(function(r) { setTimeout(r, 900 + Math.random() * 600); });

        let output = '';
        if (type === 'title') output = generateTitle(text);
        else if (type === 'bio') output = generateBio(text);
        else output = generateHashtags(text);

        result.textContent = output;
        result.classList.add('show');
        btn.disabled = false;
        btn.innerHTML = original;
      });
    });

    const overlay = document.getElementById('modal-overlay');
    const modalBody = document.getElementById('modal-body');
    const closeBtn = document.querySelector('.modal-close');

    const modalContent = {
      about: '<h2>About Us</h2><p>AI Micro-Tool was built for creators who need speed without sacrificing quality. We focus on one job at a time — generating the perfect video title, writing a catchy bio, or finding the right hashtags.</p><p>Our tools are lightweight, privacy-friendly and designed to fit into your existing workflow. No accounts, no complicated dashboards — just open, type, and generate.</p><p><strong>Mission:</strong> Empower every content creator with fast, free, AI-powered micro-tools that remove friction and spark better ideas.</p>',
      contact: '<h2>Contact Us</h2><form class="contact-form" id="contact-form"><div><label for="cname">Your Name</label><input type="text" id="cname" name="name" required placeholder="John Doe"></div><div><label for="cemail">Your Email</label><input type="email" id="cemail" name="email" required placeholder="you@example.com"></div><div><label for="cmsg">Your Message</label><textarea id="cmsg" name="message" required placeholder="How can we help?"></textarea></div><button type="submit" class="send-btn">Send Message</button></form>',
      privacy: '<h2>Privacy Policy</h2><p>Last updated: July 2026</p><h3>Information We Collect</h3><p>AI Micro-Tool does not require an account. Text you enter into the generators is processed temporarily in your browser or on our servers only to produce results and is not stored permanently.</p><h3>Cookies & Tracking</h3><p>We may use essential cookies and privacy-friendly analytics. If Google AdSense is present, Google may use cookies to serve personalized ads based on your visits to this and other sites. You can manage ad personalization via Google\'s Ad Settings.</p><h3>Third-Party Services</h3><p>We may display ads through Google AdSense. Their use of data is governed by Google\'s Privacy Policy. We do not sell your personal information.</p><h3>Your Rights</h3><p>You can request information about any data we hold or ask for deletion by contacting us through the Contact form.</p><h3>Children</h3><p>This service is not directed at children under 13. We do not knowingly collect data from children.</p>',
      terms: '<h2>Terms & Conditions</h2><p>Last updated: July 2026</p><h3>Acceptance of Terms</h3><p>By using AI Micro-Tool you agree to these Terms. If you do not agree, please do not use the service.</p><h3>Use of the Tools</h3><p>The generators are provided for personal and commercial content-creation purposes. You are responsible for the content you generate and publish. Do not use the tools for illegal, harmful, or abusive purposes.</p><h3>Intellectual Property</h3><p>You retain rights to the text you input and the outputs you generate. The website design, code and branding remain our property.</p><h3>Disclaimer</h3><p>The tools are provided "as is". We do not guarantee that generated titles, bios or hashtags will achieve any particular result. Use them as creative starting points.</p><h3>Limitation of Liability</h3><p>To the maximum extent permitted by law, AI Micro-Tool shall not be liable for any indirect or consequential damages arising from your use of the service.</p><h3>Changes</h3><p>We may update these Terms at any time. Continued use after changes constitutes acceptance.</p>'
    };

    document.querySelectorAll('[data-modal]').forEach(function(link) {
      link.addEventListener('click', function(e) {
        e.preventDefault();
        const key = link.dataset.modal;
        modalBody.innerHTML = modalContent[key];
        overlay.classList.add('open');
        document.body.style.overflow = 'hidden';

        const form = document.getElementById('contact-form');
        if (form) {
          form.addEventListener('submit', function(ev) {
            ev.preventDefault();
            const sbtn = form.querySelector('.send-btn');
            sbtn.textContent = 'Sent!';
            sbtn.disabled = true;
            setTimeout(function() {
              overlay.classList.remove('open');
              document.body.style.overflow = '';
              sbtn.textContent = 'Send Message';
              sbtn.disabled = false;
              form.reset();
            }, 1200);
          });
        }
      });
    });

    function closeModal() {
      overlay.classList.remove('open');
      document.body.style.overflow = '';
    }

    closeBtn.addEventListener('click', closeModal);
    overlay.addEventListener('click', function(e) {
      if (e.target === overlay) closeModal();
    });
    document.addEventListener('keydown', function(e) {
      if (e.key === 'Escape') closeModal();
    });
  </script>
</body>
</html>
