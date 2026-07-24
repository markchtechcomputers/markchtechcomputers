<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>manlung™ · Tech Architect & Full‑Stack Developer</title>
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Arial, Helvetica, sans-serif;
    }
    body {
      background: #0D1117;
      color: #e6edf3;
      min-height: 100vh;
      overflow-x: hidden;
    }
    /* subtle glow */
    body::before {
      content: "";
      position: fixed;
      inset: 0;
      background: radial-gradient(circle at 20% 30%, rgba(255, 215, 0, 0.04), transparent 40%),
                  radial-gradient(circle at 80% 70%, rgba(255, 69, 0, 0.04), transparent 40%);
      z-index: -2;
      pointer-events: none;
    }

    /* wrapper */
    .wrapper {
      max-width: 1100px;
      margin: 0 auto;
      padding: 40px 24px 60px;
      position: relative;
      z-index: 10;
    }

    /* ===== README CARD ===== */
    .readme-card {
      background: rgba(22, 27, 34, 0.7);
      backdrop-filter: blur(4px);
      border-radius: 32px;
      border: 1px solid rgba(255, 215, 0, 0.06);
      padding: 40px 35px;
      margin-bottom: 50px;
      box-shadow: 0 20px 60px rgba(0,0,0,0.6);
      transition: 0.3s;
    }
    .readme-card img {
      max-width: 100%;
      border-radius: 12px;
    }
    .readme-card h1, .readme-card h2, .readme-card h3 {
      color: #FFD700;
    }
    .readme-card a {
      color: #58a6ff;
      text-decoration: none;
    }
    .readme-card a:hover { text-decoration: underline; }
    .readme-card table {
      width: 100%;
      border-collapse: collapse;
      margin: 16px 0;
      background: rgba(13, 17, 23, 0.4);
      border-radius: 12px;
      overflow: hidden;
    }
    .readme-card td, .readme-card th {
      padding: 12px 16px;
      border: 1px solid rgba(255,215,0,0.06);
    }
    hr {
      border: 0;
      height: 1px;
      background: linear-gradient(90deg, rgba(255,215,0,0.1), rgba(255,215,0,0.4), rgba(255,215,0,0.1));
      margin: 28px 0;
    }

    /* ===== PORTFOLIO SECTION ===== */
    .portfolio-section {
      margin-top: 10px;
    }
    .section-title {
      font-size: 40px;
      font-weight: 700;
      text-align: center;
      color: #FFD700;
      text-shadow: 0 0 30px rgba(255,215,0,0.08);
      letter-spacing: 2px;
      margin-bottom: 40px;
      border-bottom: 2px solid rgba(255,215,0,0.08);
      padding-bottom: 18px;
    }
    .section-title i { margin-right: 14px; }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
      gap: 28px;
    }
    .project-card {
      background: rgba(22, 27, 34, 0.8);
      backdrop-filter: blur(4px);
      border-radius: 28px;
      padding: 26px 22px 28px;
      border: 1px solid rgba(255,215,0,0.05);
      transition: 0.3s ease;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
      text-align: left;
    }
    .project-card:hover {
      transform: translateY(-6px);
      border-color: #FFD700;
      box-shadow: 0 20px 50px rgba(255,215,0,0.06);
    }
    .project-card .icon {
      font-size: 40px;
      margin-bottom: 12px;
      display: inline-block;
      background: rgba(255,215,0,0.06);
      padding: 10px 14px;
      border-radius: 18px;
      color: #FFD700;
    }
    .project-card h3 {
      font-size: 22px;
      margin-bottom: 8px;
      color: #f0f6fc;
    }
    .project-card p {
      font-size: 15px;
      color: #b0b8c4;
      line-height: 1.7;
      margin-bottom: 16px;
    }
    .project-card .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-bottom: 18px;
    }
    .project-card .tags span {
      background: rgba(255,215,0,0.08);
      color: #FFD700;
      padding: 3px 14px;
      border-radius: 30px;
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 0.3px;
    }
    .project-card .btn {
      display: inline-block;
      padding: 8px 22px;
      background: transparent;
      border: 1.5px solid #FFD700;
      color: #FFD700;
      border-radius: 40px;
      font-weight: 600;
      font-size: 14px;
      transition: 0.3s;
      text-decoration: none;
      letter-spacing: 0.5px;
    }
    .project-card .btn:hover {
      background: #FFD700;
      color: #0D1117;
      box-shadow: 0 0 30px rgba(255,215,0,0.15);
    }

    /* footer */
    .footer {
      text-align: center;
      margin-top: 60px;
      padding: 28px 0 10px;
      border-top: 1px solid rgba(255,215,0,0.04);
      color: #8b949e;
      font-size: 15px;
      letter-spacing: 0.5px;
    }
    .footer i { color: #FFD700; margin: 0 4px; }

    /* responsive */
    @media (max-width: 768px) {
      .wrapper { padding: 24px 14px 40px; }
      .readme-card { padding: 24px 18px; }
      .readme-card table, .readme-card td, .readme-card th { font-size: 14px; }
      .section-title { font-size: 30px; }
      .grid { grid-template-columns: 1fr; }
    }
    @media (max-width: 480px) {
      .readme-card { padding: 16px 12px; }
    }
  </style>
</head>
<body>

  <div class="wrapper">
    <!-- ===== README CONTENT ===== -->
    <div class="readme-card">
      <!-- 🚧 ANIMATED BANNER -->
      <p align="center">
        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:FFD700,100:FF4500&height=180&section=header&text=manlung™&fontSize=60&fontColor=fff&animation=twinkling" width="100%" />
      </p>

      <!-- 👋 INTRO -->
      <h1 align="center">
        <img src="https://raw.githubusercontent.com/ABSphreak/ABSphreak/master/gifs/Hi.gif" width="30px" /> 
        I'm <span style="color:#FFD700;">Adict Manlung</span>
      </h1>

      <h3 align="center">
        <span style="color:#ffaa00;">Tech Architect</span> · 
        <span style="color:#00ccff;">Full‑Stack Developer</span> · 
        <span style="color:#ff6b6b;">Digital Artisan</span>
      </h3>

      <p align="center">
        <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=FFD700&center=true&vCenter=true&width=600&lines=Building+the+future%2C+one+line+at+a+time;Full‑Stack+%7C+Cloud+%7C+AI+Enthusiast;Scalable+systems+%26+clean+code" alt="Typing SVG" />
      </p>

      <hr />

      <!-- 🧠 ABOUT ME -->
      <div align="center">
        <table>
          <tr>
            <td width="60%">
              <h2>🧠 <span style="color:#FFD700;">About Me</span></h2>
              <p style="font-size:16px; line-height:1.8;">
                🔹 <strong>Tech Architect</strong> with a passion for <strong>scalable systems</strong> and <strong>clean code</strong>.<br />
                🔹 Currently diving deep into <strong>Cloud Native</strong> & <strong>AI‑driven development</strong>.<br />
                🔹 I turn complex problems into <strong>elegant solutions</strong> — from idea to deployment.<br />
                🔹 <strong>📍 Nairobi, Kenya</strong> · Open to global collaborations.
              </p>
              <p>
                <img src="https://komarev.com/ghpvc/?username=markchtechcomputers&label=Profile%20Views&color=FFD700&style=flat-square" alt="profile views" />
                <img src="https://img.shields.io/github/followers/markchtechcomputers?label=Followers&style=social" />
              </p>
            </td>
            <td width="40%" align="center">
              <img src="https://github-readme-stats.vercel.app/api?username=markchtechcomputers&show_icons=true&theme=radical&hide_border=true&bg_color=0D1117&title_color=FFD700&icon_color=FF4500" width="100%" />
            </td>
          </tr>
        </table>
      </div>

      <hr />

      <!-- 🛠️ SKILLS -->
      <h2 align="center">⚡ <span style="color:#FFD700;">Tech Stack & Expertise</span></h2>
      <p align="center">
        <img src="https://skillicons.dev/icons?i=js,ts,react,next,nodejs,py,go,rust,java,spring,aws,azure,docker,kubernetes,terraform,jenkins,grafana,kafka,redis,mongodb,postgres,mysql,nginx,linux,bash,vim,git,githubactions" />
      </p>
      <div align="center">
        <table>
          <tr><td><strong>🌐 Frontend</strong></td><td>React · Next.js · Vue · Tailwind · Framer</td></tr>
          <tr><td><strong>⚙️ Backend</strong></td><td>Node.js · Python · Go · Rust · Spring Boot · .NET Core</td></tr>
          <tr><td><strong>☁️ Cloud & DevOps</strong></td><td>AWS · Azure · GCP · Docker · Kubernetes · Terraform · CI/CD</td></tr>
          <tr><td><strong>🗄️ Databases</strong></td><td>PostgreSQL · MongoDB · Redis · MySQL · Cassandra</td></tr>
          <tr><td><strong>🧪 Tools</strong></td><td>Git · Linux · Vim · Grafana · Prometheus · Kafka · Nginx</td></tr>
        </table>
      </div>

      <hr />

      <!-- 📈 GITHUB STATS -->
      <h2 align="center">📊 <span style="color:#FFD700;">GitHub Analytics</span></h2>
      <div align="center">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=markchtechcomputers&theme=dark&hide_border=true&background=0D1117&stroke=FFD700&ring=FF4500&fire=FFD700&currStreakLabel=FFD700" width="49%" />
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=markchtechcomputers&layout=compact&theme=radical&hide_border=true&bg_color=0D1117&title_color=FFD700" width="49%" />
      </div>

      <hr />

      <!-- 🤝 CONNECT -->
      <h2 align="center">📫 <span style="color:#FFD700;">Let's Connect</span></h2>
      <p align="center">
        <a href="mailto:adict@manlung.co.ke"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
        <a href="https://linkedin.com/in/adictmanlung"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
        <a href="https://twitter.com/manlung_ke"><img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" /></a>
        <a href="https://manlung.co.ke"><img src="https://img.shields.io/badge/Portfolio-FFD700?style=for-the-badge&logo=google-chrome&logoColor=black" /></a>
        <a href="https://github.com/markchtechcomputers"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
      </p>
      <p align="center">
        <img src="https://img.shields.io/badge/📞-+254%20724%20356%20178-green?style=flat-square&logo=whatsapp&logoColor=white" />
      </p>

      <hr />

      <!-- 🧩 FUN -->
      <h2 align="center">🧩 <span style="color:#FFD700;">Knowledge & Interests</span></h2>
      <div align="center">
        <table>
          <tr><td>📌 <strong>Currently learning</strong></td><td>Kubernetes Operators · Rust · AI/ML (PyTorch)</td></tr>
          <tr><td>📌 <strong>Looking to collaborate on</strong></td><td>Open‑source DevOps tools · Fintech · EdTech projects</td></tr>
          <tr><td>📌 <strong>Fun fact</strong></td><td>I once debugged a production issue at 3am with a cup of coffee ☕ and a rubber duck 🦆</td></tr>
          <tr><td>📌 <strong>Pronouns</strong></td><td>He / Him</td></tr>
        </table>
      </div>

      <hr />

      <!-- 🚧 FOOTER -->
      <p align="center">
        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF4500,100:FFD700&height=120&section=footer" width="100%" />
      </p>
      <p align="center">
        <i>“Building the digital future — one commit at a time.”</i> 🚀
      </p>
    </div>

    <!-- ===== PORTFOLIO SECTION ===== -->
    <div class="portfolio-section">
      <div class="section-title"><i class="fas fa-briefcase"></i> Portfolio / Projects</div>
      <div class="grid">
        <!-- Project 1 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-cloud-upload-alt"></i></div>
          <h3>CloudScale DevOps</h3>
          <p>End-to-end CI/CD pipeline with Kubernetes, Terraform, and AWS. Reduced deployment time by 70%.</p>
          <div class="tags"><span>AWS</span><span>K8s</span><span>Terraform</span><span>GitHub Actions</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
        <!-- Project 2 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-robot"></i></div>
          <h3>AI Insight Engine</h3>
          <p>Real-time analytics platform using Python, PyTorch, and Redis. Predicts user behavior with 92% accuracy.</p>
          <div class="tags"><span>Python</span><span>PyTorch</span><span>Redis</span><span>FastAPI</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
        <!-- Project 3 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-store"></i></div>
          <h3>EcoShop Marketplace</h3>
          <p>Full-stack e-commerce with Next.js, Node.js, and MongoDB. Integrated payments, real-time inventory.</p>
          <div class="tags"><span>Next.js</span><span>Node.js</span><span>MongoDB</span><span>Stripe</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
        <!-- Project 4 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-shield-alt"></i></div>
          <h3>SecureAuth Zero</h3>
          <p>Passwordless authentication system using WebAuthn, JWT, and Rust. Deployed on Azure.</p>
          <div class="tags"><span>Rust</span><span>WebAuthn</span><span>Azure</span><span>JWT</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
        <!-- Project 5 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-chart-line"></i></div>
          <h3>FinDash Analytics</h3>
          <p>Interactive dashboard for fintech with D3.js, Go, and Kafka. Processes 10k+ events/sec.</p>
          <div class="tags"><span>Go</span><span>Kafka</span><span>D3.js</span><span>PostgreSQL</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
        <!-- Project 6 -->
        <div class="project-card">
          <div class="icon"><i class="fas fa-mobile-alt"></i></div>
          <h3>HealthTrack Mobile</h3>
          <p>Cross-platform health app with React Native, Node.js, and GraphQL. Used by 5k+ users.</p>
          <div class="tags"><span>React Native</span><span>GraphQL</span><span>Node.js</span><span>PostgreSQL</span></div>
          <a href="#" class="btn">View Case <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
    </div>

    <!-- footer -->
    <div class="footer">
      <i class="fas fa-crown"></i> manlung™ · Tech Architect · <i class="fas fa-code"></i> Building the future, one commit at a time.
    </div>
  </div>

  <!-- Background Audio – auto plays, loops (hidden) -->
  <audio id="bgAudio" loop autoplay style="display: none;">
    <source src="https://outside-plum-jcpixw2i.edgeone.dev/" type="audio/mpeg" />
    Your browser does not support the audio element.
  </audio>

  <script>
    (function() {
      const audio = document.getElementById('bgAudio');
      const playAudio = () => {
        audio.play().catch(() => {
          const resume = () => {
            audio.play().then(() => {
              document.removeEventListener('click', resume);
              document.removeEventListener('touchstart', resume);
            }).catch(e => {});
          };
          document.addEventListener('click', resume);
          document.addEventListener('touchstart', resume);
        });
      };
      if (document.readyState === 'complete') playAudio();
      else window.addEventListener('load', playAudio);
      audio.addEventListener('ended', function() {
        this.currentTime = 0;
        this.play().catch(() => {});
      });
    })();
  </script>
</body>
</html>
