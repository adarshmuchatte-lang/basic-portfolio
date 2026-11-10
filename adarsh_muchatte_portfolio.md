<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Adarsh Muchatte – Full-stack, Cloud & 3D Web Portfolio</title>
<meta name="description" content="Portfolio of Adarsh Muchatte, B.Tech IT student at VIT Vellore, specialising in full-stack web development, AWS cloud architectures, AI applications, and immersive 3D experiences.">
<meta name="theme-color" content="#000000">
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@500;800&family=Hanken+Grotesk:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{--bg:#000000;--ink:#ffffff;--muted:#888888;--deep:#0a0a0a;--glass:rgba(255,255,255,0.03);--glass-border:rgba(255,255,255,0.08);
 box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
*,*::before,*::after{box-sizing:inherit}
html{scroll-behavior:smooth;background:var(--bg)}
body{margin:0;color:var(--ink);font:400 17px/1.6 'Hanken Grotesk',system-ui,sans-serif;background:var(--bg);overflow-x:hidden}
canvas#gl{position:fixed;inset:0;width:100%;height:100%;z-index:0;pointer-events:none}
main{position:relative;z-index:1}

/* Header & Nav */
header.site-nav{position:fixed;top:0;left:0;width:100%;z-index:100;display:flex;justify-content:space-between;align-items:center;padding:1.5rem 7vw;background:rgba(0,0,0,0.7);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);border-bottom:1px solid var(--glass-border);transition:padding .3s ease}
.nav-brand{font-family:'Unbounded',system-ui,sans-serif;font-weight:800;font-size:1rem;color:var(--ink);text-decoration:none;letter-spacing:-.02em}
.nav-links{display:flex;gap:2rem;list-style:none;margin:0;padding:0}
.nav-links a{color:var(--muted);text-decoration:none;font-size:.9rem;font-weight:500;transition:color .2s ease}
.nav-links a:hover,.nav-links a.active{color:var(--ink)}

section{padding:12vh 7vw;max-width:1300px;margin:0 auto}
section.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;position:relative}

h1,h2,h3{font-family:'Unbounded',system-ui,sans-serif;margin:0;line-height:1.08;letter-spacing:-.02em}
h1{font-weight:800;font-size:clamp(3rem,9vw,8rem);color:var(--ink)}
h2{font-weight:500;font-size:clamp(1.8rem,3.5vw,2.8rem);margin-bottom:2.5rem}
p{max-width:62ch;margin:0;color:#cccccc}

.badge-availability{display:inline-flex;align-items:center;gap:.6rem;padding:.4rem 1rem;border-radius:99px;background:rgba(255,255,255,0.06);border:1px solid var(--glass-border);font-size:.85rem;font-weight:500;width:fit-content;margin-bottom:1.5rem}
.badge-dot{width:8px;height:8px;background:#4ade80;border-radius:50%;box-shadow:0 0 8px #4ade80;animation:pulse 2s infinite}
@keyframes pulse{0%{opacity:1}50%{opacity:.4}100%{opacity:1}}

.role{font-size:clamp(1.05rem,1.8vw,1.35rem);margin-top:1.4rem;max-width:50ch;color:#dddddd}
.btns{display:flex;flex-wrap:wrap;gap:1rem;margin-top:2.2rem}
.btn{font:500 1rem 'Hanken Grotesk',sans-serif;padding:.9rem 1.6rem;border-radius:99px;background:var(--ink);color:var(--bg);text-decoration:none;border:0;cursor:pointer;transition:transform .25s, background .25s, color .25s;display:inline-flex;align-items:center;gap:.5rem}
.btn.alt{background:transparent;color:var(--ink);border:1px solid rgba(255,255,255,0.2)}
.btn:hover,.btn:focus-visible{transform:scale(1.04);outline:3px solid var(--ink);outline-offset:3px}

.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(320px,1fr));gap:1.5rem}
.card{padding:2rem;border-radius:24px;background:var(--glass);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);border:1px solid var(--glass-border);transition:transform .25s ease-out, border-color .25s ease-out;position:relative;overflow:hidden}
.card:hover{border-color:rgba(255,255,255,0.3)}
.card h3{font-size:1.2rem;color:var(--ink);margin-bottom:.4rem}
.card .meta{font-size:.85rem;color:var(--muted);margin-bottom:1rem;font-weight:500}
.card p{font-size:.95rem;margin-top:.6rem}
.card.wide{grid-column:1/-1}

.tags{display:flex;flex-wrap:wrap;gap:.5rem;margin-top:1.2rem}
.tags span{font-size:.75rem;padding:.2rem .75rem;border-radius:99px;background:rgba(255,255,255,0.05);color:#dddddd;border:1px solid var(--glass-border);font-weight:500}

ul{margin:.6rem 0 0;padding-left:1.2rem;color:#cccccc}
li{margin:.4rem 0;font-size:.95rem}

.skill-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.5rem}
.skill-card h3{font-size:1rem;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;margin-bottom:.8rem}
.skill-list{display:flex;flex-wrap:wrap;gap:.5rem}
.skill-tag{font-size:.9rem;padding:.4rem .9rem;border-radius:12px;background:rgba(255,255,255,0.04);border:1px solid var(--glass-border);color:var(--ink)}

.project-links{display:flex;gap:1.2rem;margin-top:1.5rem;font-size:.9rem;font-weight:500}
.project-links a{color:var(--ink);text-decoration:none;display:inline-flex;align-items:center;gap:.4rem;opacity:.8;transition:opacity .2s}
.project-links a:hover{opacity:1;text-decoration:underline}

.contact-section{background:radial-gradient(circle at center, rgba(255,255,255,0.03) 0%, transparent 70%);border-top:1px solid var(--glass-border)}
.contact-grid{display:grid;grid-template-columns:1fr auto;gap:2rem;align-items:center}
@media(max-width:768px){.contact-grid{grid-template-columns:1fr}.nav-links{display:none}}

.contact-info-list{display:flex;flex-direction:column;gap:.8rem;margin-top:2rem;font-size:1.05rem}
#mail{user-select:all;font-weight:600;color:var(--ink)}
#msg{min-height:1.5em;margin-top:.8rem;font-size:.95rem;color:#4ade80}

.mq{overflow:hidden;white-space:nowrap;padding:1.2rem 0;transform:rotate(-2deg);margin:4rem -4vw;background:var(--ink);color:var(--bg);font:800 clamp(1.1rem,2.5vw,1.8rem) 'Unbounded',sans-serif;box-shadow:0 10px 30px rgba(0,0,0,0.5)}
.mq div{display:inline-block;animation:mq 28s linear infinite}
@keyframes mq{to{transform:translateX(-50%)}}

h1{animation:gl 6s infinite steps(1)}
@keyframes gl{0%,91%,100%{text-shadow:none;transform:none}93%{text-shadow:4px 0 #666,-4px 0 #aaa;transform:translateX(3px) skewX(-3deg)}95%{text-shadow:-6px 2px #555,6px -2px #bbb;transform:translateX(-4px)}97%{text-shadow:2px 0 #fff;transform:skewX(2deg)}}

.card{background:radial-gradient(300px circle at var(--mx,50%) var(--my,50%),rgba(255,255,255,.06),transparent 65%),var(--glass);opacity:0;translate:0 40px;transition:transform .25s ease-out,opacity .8s,translate .8s cubic-bezier(.2,.8,.2,1),border-color .25s}
.card.in{opacity:1;translate:0 0}
.bp{position:fixed;border-radius:50%;pointer-events:none;z-index:9}
#pb{position:fixed;top:0;left:0;height:2px;width:100%;transform-origin:left;transform:scaleX(0);background:var(--ink);z-index:15}
.hint{margin-top:1.2rem;font-size:.9rem;color:var(--muted)}

footer{padding:5vh 7vw;font-size:.9rem;color:var(--muted);position:relative;z-index:1;border-top:1px solid var(--glass-border);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1rem}

#cur{position:fixed;width:20px;height:20px;border-radius:50%;border:2px solid rgba(255,255,255,0.5);pointer-events:none;z-index:999;transform:translate(-50%,-50%);transition:width .2s,height .2s,background .2s,border-color .2s}
#cur.big{width:50px;height:50px;background:rgba(255,255,255,.1);border-color:var(--ink)}

#load{position:fixed;inset:0;z-index:1000;background:var(--deep);display:grid;place-items:center;font-family:'Unbounded',sans-serif;font-size:1.5rem;color:var(--ink);transition:opacity .8s ease}
#load div{text-align:center}
#load i{display:block;height:2px;width:0;background:var(--ink);margin-top:1rem;transition:width 1s ease}

@media (hover:none){#cur{display:none}}
@media (prefers-reduced-motion:reduce){html{scroll-behavior:auto}*{transition:none!important;animation:none!important}.card{opacity:1;translate:none}}
</style>
</head>
<body>
<div id="load"><div>Adarsh Muchatte<i id="bar"></i></div></div>
<div id="cur" aria-hidden="true"></div>
<div id="pb" aria-hidden="true"></div>
<canvas id="gl" aria-hidden="true"></canvas>

<header class="site-nav">
 <a class="nav-brand" href="#top">AM.</a>
 <ul class="nav-links">
  <li><a href="#about">About</a></li>
  <li><a href="#skills">Skills</a></li>
  <li><a href="#projects">Projects</a></li>
  <li><a href="#credentials">Credentials</a></li>
  <li><a href="#contact">Contact</a></li>
 </ul>
</header>

<main>

<section class="hero" id="top">
 <div class="badge-availability"><span class="badge-dot"></span> Available for Software & AI Internships</div>
 <h1><span data-s>Adarsh</span><br><span data-s>Muchatte</span></h1>
 <div class="role">B.Tech IT student at VIT Vellore. Architecting robust full-stack systems, cloud solutions, AI applications, and immersive 3D web experiences.</div>
 <div class="hint">Tip: Move your mouse, scroll to navigate the 3D space, click anywhere, or press W to warp.</div>
 <div class="btns">
  <a class="btn" href="#projects">Explore My Work</a>
  <a class="btn alt" href="#contact">Contact Me</a>
 </div>
</section>

<div class="mq" aria-hidden="true"><div><span>Full-stack ✦ AWS ✦ Three.js ✦ 3D web ✦ AI applications ✦ Node.js ✦ IoT ✦ C++ & Java ✦ Full-stack ✦ AWS ✦ Three.js ✦ 3D web ✦ AI applications ✦ Node.js ✦ IoT ✦ C++ & Java ✦ </span><span>Full-stack ✦ AWS ✦ Three.js ✦ 3D web ✦ AI applications ✦ Node.js ✦ IoT ✦ C++ & Java ✦ Full-stack ✦ AWS ✦ Three.js ✦ 3D web ✦ AI applications ✦ Node.js ✦ IoT ✦ C++ & Java ✦ </span></div></div>

<section id="about">
 <h2>About</h2>
 <p>I am a B.Tech Information Technology student at VIT Vellore (Register Number: 24BIT0130) with a strong passion for software engineering, cloud architecture, and experimental frontend development. I build scalable applications, backend systems on AWS, and high-performance interactive 3D web experiences.</p>
 <p style="margin-top:1.2rem">My practical approach combines rigorous data structures and algorithms practice in C++ and Java with modern web technologies. I am actively seeking software engineering, full-stack, or AI application internship opportunities where I can contribute to impactful engineering teams.</p>
</section>

<section id="skills">
 <h2>Technical Skills</h2>
 <div class="skill-grid">
  <div class="card skill-card">
   <h3>Programming Languages</h3>
   <div class="skill-list"><span class="skill-tag">Java</span><span class="skill-tag">C</span><span class="skill-tag">C++</span><span class="skill-tag">Python</span><span class="skill-tag">JavaScript</span><span class="skill-tag">SQL</span></div>
  </div>
  <div class="card skill-card">
   <h3>Frontend Development</h3>
   <div class="skill-list"><span class="skill-tag">HTML5</span><span class="skill-tag">CSS3</span><span class="skill-tag">JavaScript (ES6+)</span><span class="skill-tag">Three.js</span><span class="skill-tag">Responsive Design</span><span class="skill-tag">REST APIs</span><span class="skill-tag">React.js (Learning)</span><span class="skill-tag">Express.js (Learning)</span><span class="skill-tag">MongoDB (Learning)</span></div>
  </div>
  <div class="card skill-card">
   <h3>Cloud &amp; Backend</h3>
   <div class="skill-list"><span class="skill-tag">Node.js</span><span class="skill-tag">AWS Lambda</span><span class="skill-tag">Amazon Cognito</span><span class="skill-tag">API Gateway</span><span class="skill-tag">DynamoDB</span><span class="skill-tag">AWS SAM / CloudFormation</span><span class="skill-tag">PostgreSQL</span><span class="skill-tag">Flask</span></div>
  </div>
  <div class="card skill-card">
   <h3>AI &amp; Generative AI</h3>
   <div class="skill-list"><span class="skill-tag">Prompt Engineering</span><span class="skill-tag">LLM Concepts</span><span class="skill-tag">Amazon Bedrock</span><span class="skill-tag">Generative AI Integration</span></div>
  </div>
  <div class="card skill-card">
   <h3>Embedded Systems &amp; IoT</h3>
   <div class="skill-list"><span class="skill-tag">Arduino</span><span class="skill-tag">RFID (MFRC522)</span><span class="skill-tag">PIR Sensors</span><span class="skill-tag">GSM Module</span><span class="skill-tag">Embedded C/C++</span></div>
  </div>
  <div class="card skill-card">
   <h3>Developer Tools</h3>
   <div class="skill-list"><span class="skill-tag">Git</span><span class="skill-tag">GitHub (adarshmuchatte-lang)</span><span class="skill-tag">VS Code</span><span class="skill-tag">PowerShell</span><span class="skill-tag">Netlify</span><span class="skill-tag">Microsoft Power BI</span></div>
  </div>
 </div>
</section>

<section id="projects">
 <h2>Featured Projects</h2>
 <div class="grid">
  
  <div class="card wide">
   <h3>CloudArchitect AI</h3>
   <div class="meta">AWS Architecture Recommendation Platform · Team CloudCrafters</div>
   <p>An intelligent system designed to generate tailored AWS architecture recommendations for cloud deployments.</p>
   <ul>
    <li>Engineered the backend using AWS API Gateway and AWS Lambda, integrating Amazon Cognito for secure user authentication and DynamoDB for persistent recommendation history.</li>
    <li>Implemented deterministic rule-based architecture selection combined with Amazon Bedrock (Nova Lite) solely for generating natural language explanations.</li>
    <li>Added an interactive architecture graph with PNG/SVG export capabilities and automated deployment workflows via AWS SAM/CloudFormation and PowerShell scripts.</li>
   </ul>
   <div class="tags"><span>Node.js 20</span><span>AWS Lambda</span><span>API Gateway</span><span>Cognito</span><span>DynamoDB</span><span>Amazon Bedrock</span><span>AWS SAM</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub Repository ↗</a>
   </div>
  </div>

  <div class="card">
   <h3>ECLIPSE: The Last Frontier</h3>
   <div class="meta">3D Space-Journey Immersive Experience</div>
   <p>A scroll-driven interactive web experience guiding visitors past unknown planetary worlds, through a relativistic wormhole, and toward a black hole destination.</p>
   <div class="tags"><span>Lovable</span><span>TanStack</span><span>Vite</span><span>Netlify</span><span>Three.js</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
    <span style="opacity:0.5">• Live Demo (Placeholder)</span>
   </div>
  </div>

  <div class="card">
   <h3>ABYSS: The Last Frontier</h3>
   <div class="meta">Underwater Deep-Sea Exploration Website</div>
   <p>An immersive vertical scroll dive through ocean depth zones featuring real-time depth readouts, deep-sea fauna documentation, and atmospheric oceanography facts.</p>
   <div class="tags"><span>HTML5</span><span>CSS3</span><span>JavaScript</span><span>Scroll Animations</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
    <span style="opacity:0.5">• Live Demo (Placeholder)</span>
   </div>
  </div>

  <div class="card">
   <h3>SentiBot</h3>
   <div class="meta">AI Sentiment Analysis Chatbot</div>
   <p>An interactive conversational application featuring real-time sentiment scoring, comprehensive analytics views, and export functionality for chat logs.</p>
   <div class="tags"><span>Python</span><span>Flask</span><span>PostgreSQL</span><span>Replit</span><span>NLP</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
   </div>
  </div>

  <div class="card">
   <h3>Smart Luggage Security and Alarm</h3>
   <div class="meta">IoT Baggage-Theft Alert System · VIT Vellore</div>
   <p>An embedded hardware security system integrating an RFID reader for access control, a PIR motion sensor for intrusion detection, and a GSM module for remote alerts.</p>
   <div class="tags"><span>Arduino</span><span>RFID (MFRC522)</span><span>PIR Sensor</span><span>GSM Module</span><span>Embedded C/C++</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
   </div>
  </div>

  <div class="card">
   <h3>Exodus</h3>
   <div class="meta">3D Sci-Fi Spaceship Experience</div>
   <p>An interactive 3D visualization showcasing the EXODUS-01 generation ship, complete with deep-space environments and simulated mission telemetry.</p>
   <div class="tags"><span>HTML5</span><span>JavaScript</span><span>WebGL</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
   </div>
  </div>

  <div class="card">
   <h3>Dimensional Portal</h3>
   <div class="meta">3D Portal Web Experience</div>
   <p>An experimental interactive 3D web environment built around sci-fi dimensional portals with dynamic particle systems and cinematic lighting.</p>
   <div class="tags"><span>Three.js</span><span>Particle Systems</span><span>WebGL</span></div>
   <div class="project-links">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
   </div>
  </div>

  <div class="card wide">
   <h3>Additional Systems, AI &amp; Data Projects</h3>
   <p><b>AI, Cloud &amp; Data:</b> AI Chatbot with prompt engineering, AI Resume Analyzer concept, AI-based accident and driver risk detection, storage tier recommendation system for medical image repositories, Sales Analytics Dashboard in Power BI, and Smart Power Consumption Optimization IoT concepts.</p>
   <p style="margin-top:.8rem"><b>Systems &amp; Embedded:</b> Library Management System in C, Hospital Management System modeling and requirements specification, memory-mapped concurrent file analyzer, and Smart Shopping Management System.</p>
   <div class="project-links" style="margin-top:1.2rem">
    <a href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">Explore GitHub Profile for Full Repository List ↗</a>
   </div>
  </div>

 </div>
</section>

<section id="credentials">
 <h2>Education, Certifications &amp; Achievements</h2>
 <div class="grid">
  
  <div class="card">
   <h3>Certifications</h3>
   <ul>
    <li>Python for Data Science – IBM Skills Network (Oct 2026)</li>
    <li>AI Literacy – IBM (Jul 2026)</li>
    <li>AI for Beginners – HP LIFE (Jul 2026)</li>
    <li>Prompt Engineering – One Million Prompters</li>
    <li>Introduction to Generative AI – AWS</li>
    <li>Introduction to Machine Learning – Kaggle</li>
    <li>MongoDB Atlas &amp; Developing AI Solutions on Azure</li>
   </ul>
  </div>

  <div class="card">
   <h3>Virtual Job Simulations</h3>
   <div class="meta">Completed via Forage (Training &amp; Simulation programs)</div>
   <ul>
    <li>Skyscanner Front-End Engineering</li>
    <li>BCG X GenAI</li>
    <li>TCS GenAI Data Analytics</li>
    <li>British Airways Data Science</li>
    <li>Deloitte Data Analytics</li>
    <li>BCG Platinion IT Architecture</li>
    <li>Goldman Sachs Internal Audit</li>
   </ul>
  </div>

  <div class="card">
   <h3>Education &amp; Achievements</h3>
   <p><b>VIT Vellore</b><br>B.Tech Information Technology (2024 – 2028)<br>Register Number: 24BIT0130</p>
   <p style="margin-top:.8rem"><b>Academic Background</b><br>Class XII: 72% | Class X: 95.4%</p>
   <p style="margin-top:.8rem"><b>Achievements &amp; Competitions</b><br>HackerRank Orchestrate, Halloween Edition (Registered Participant)<br>MHT CET 2024: 97.85 Percentile (PCM)</p>
  </div>

 </div>
</section>

<section class="contact-section" id="contact">
 <h2>Contact &amp; Resume</h2>
 <p>Looking for a dedicated software engineering, full-stack, or AI application intern. Let's connect.</p>
 
 <div class="btns">
  <a class="btn" id="gmail-btn" href="https://mail.google.com/mail/?view=cm&fs=1&to=adarshmuchatte@gmail.com&su=Hello%20Adarsh" target="_blank" rel="noopener noreferrer">Write in Gmail</a>
  <button class="btn alt" id="copy" type="button">Copy Email Address</button>
  <a class="btn alt" href="https://www.linkedin.com/in/adarshmuchatte" target="_blank" rel="noopener noreferrer">LinkedIn Profile</a>
  <a class="btn alt" href="https://github.com/adarshmuchatte-lang" target="_blank" rel="noopener noreferrer">GitHub Profile</a>
  <!-- Placeholder for Resume download until provided -->
  <a class="btn alt" href="#resume-placeholder" onclick="alert('Resume file is currently pending upload. Please contact via email or LinkedIn for the latest copy.'); return false;">Download Resume (PDF Placeholder)</a>
 </div>

 <div class="contact-info-list">
  <div>Email: <span id="mail">adarshmuchatte@gmail.com</span></div>
  <div>Institution: Vellore Institute of Technology (VIT), Vellore</div>
 </div>
 <div id="msg" role="status"></div>
</section>

</main>

<footer>
 <div>© 2026 Adarsh Muchatte. All rights reserved.</div>
 <div>B.Tech Information Technology • VIT Vellore</div>
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
 var mailEl=document.getElementById('mail'),msg=document.getElementById('msg');
 document.getElementById('copy').addEventListener('click',function(){
  var t=mailEl.textContent.trim();
  function done(ok){
   msg.textContent=ok?'Email copied to clipboard: '+t:'Could not copy automatically. Please select and copy manually.';
   if(!ok){var r=document.createRange();r.selectNodeContents(mailEl);var s=getSelection();s.removeAllRanges();s.addRange(r)}
  }
  function fallback(){try{var a=document.createElement('textarea');a.value=t;a.style.position='fixed';a.style.opacity='0';document.body.appendChild(a);a.select();var ok=document.execCommand('copy');a.remove();done(ok)}catch(e){done(false)}}
  if(navigator.clipboard&&navigator.clipboard.writeText){navigator.clipboard.writeText(t).then(function(){done(true)},fallback)}else fallback();
 });

 var reduce=matchMedia('(prefers-reduced-motion:reduce)').matches;
 var canvas=document.getElementById('gl');
 var renderer=new THREE.WebGLRenderer({canvas:canvas,antialias:true,alpha:true});
 var mobile=innerWidth<700;
 renderer.setPixelRatio(Math.min(devicePixelRatio,mobile?1.5:2));
 var scene=new THREE.Scene();
 var cam=new THREE.PerspectiveCamera(50,1,.1,100);cam.position.z=6;

 var uni={t:{value:0},amp:{value:.35},c1:{value:new THREE.Color('#ffffff')},c2:{value:new THREE.Color('#0a0a0a')}};
 var mat=new THREE.ShaderMaterial({uniforms:uni,
  vertexShader:'uniform float t,amp;varying vec3 n;varying vec3 v;void main(){vec3 p=position;float d=sin(p.x*2.1+t)*sin(p.y*2.3+t*1.2)*sin(p.z*2.0+t*.8);p+=normal*d*amp;n=normalize(normalMatrix*normal);vec4 mv=modelViewMatrix*vec4(p,1.);v=normalize(-mv.xyz);gl_Position=projectionMatrix*mv;}',
  fragmentShader:'uniform vec3 c1,c2;varying vec3 n;varying vec3 v;void main(){float f=pow(1.-max(dot(normalize(n),normalize(v)),0.),2.2);vec3 col=mix(c2,c1,smoothstep(-.2,1.,n.y*.6+f));col+=f*.3;gl_FragColor=vec4(col,1.);}'});
 var blob=new THREE.Mesh(new THREE.IcosahedronGeometry(1.6,mobile?32:64),mat);
 scene.add(blob);
 var rings=new THREE.Group();
 for(var i=0;i<3;i++){var r=new THREE.Mesh(new THREE.TorusGeometry(2.4+i*.45,.012,8,160),new THREE.MeshBasicMaterial({color:0xffffff,transparent:true,opacity:.25-i*.06}));r.rotation.set(i*1.1,i*.7,0);rings.add(r)}
 blob.add(rings);
 var N=mobile?400:1000,pos=new Float32Array(N*3);
 for(var k=0;k<N*3;k++)pos[k]=(Math.random()-.5)*30;
 var pg=new THREE.BufferGeometry();pg.setAttribute('position',new THREE.BufferAttribute(pos,3));
 var pts=new THREE.Points(pg,new THREE.PointsMaterial({size:.025,color:0xffffff,transparent:true,opacity:.35}));
 scene.add(pts);
 var shapes=[],geos=[new THREE.OctahedronGeometry(.5),new THREE.TorusKnotGeometry(.35,.1,64,8),new THREE.IcosahedronGeometry(.45),new THREE.TetrahedronGeometry(.55)];
 for(var q=0;q<(mobile?6:12);q++){var sm=new THREE.Mesh(geos[q%4],new THREE.MeshBasicMaterial({color:0xffffff,wireframe:true,transparent:true,opacity:.15}));sm.position.set((Math.random()-.5)*16,(Math.random()-.5)*10,(Math.random()-.5)*8-2);sm.userData={s:Math.random()*.015+.004,o:Math.random()*6};scene.add(sm);shapes.push(sm)}

 function resize(){var w=innerWidth,h=innerHeight;renderer.setSize(w,h,false);cam.aspect=w/h;cam.updateProjectionMatrix();mobile=w<700}
 addEventListener('resize',resize);resize();

 var mx=0,my=0,sx=0,sy=0,prog=0,sp=0,hover=0,hoverT=0;
 var ray=new THREE.Raycaster(),m2=new THREE.Vector2(),cur=document.getElementById('cur');
 addEventListener('pointermove',function(e){
  mx=e.clientX/innerWidth*2-1;my=-(e.clientY/innerHeight*2-1);
  cur.style.left=e.clientX+'px';cur.style.top=e.clientY+'px';
  m2.set(mx,my);ray.setFromCamera(m2,cam);
  hoverT=ray.intersectObject(blob).length?1:0;
  cur.classList.toggle('big',!!(hoverT||e.target.closest('a,button,.card')))});
 var lastY=0,vel=0;
 addEventListener('scroll',function(){var h=document.documentElement.scrollHeight-innerHeight;prog=h>0?scrollY/h:0;vel=Math.min(vel+Math.abs(scrollY-lastY)/80,3);lastY=scrollY},{passive:true});
 addEventListener('pointerdown',function(){if(hoverT)vel=3});

 document.querySelectorAll('.card').forEach(function(c){
  c.addEventListener('pointermove',function(e){var b=c.getBoundingClientRect(),x=(e.clientX-b.left)/b.width-.5,y=(e.clientY-b.top)/b.height-.5;c.style.transform='perspective(800px) rotateY('+x*4+'deg) rotateX('+-y*4+'deg)';c.style.setProperty('--mx',(x+.5)*100+'%');c.style.setProperty('--my',(y+.5)*100+'%')});
  c.addEventListener('pointerleave',function(){c.style.transform=''})});

 var A=[new THREE.Color('#ffffff'),new THREE.Color('#cccccc'),new THREE.Color('#eeeeee'),new THREE.Color('#888888'),new THREE.Color('#ffffff')];
 var B=[new THREE.Color('#050505'),new THREE.Color('#000000'),new THREE.Color('#0f0f0f'),new THREE.Color('#020202'),new THREE.Color('#050505')];
 function stops(S,p,out){var f=p*(S.length-1),i=Math.min(Math.floor(f),S.length-2);out.copy(S[i]).lerp(S[i+1],f-i)}

 var clock=new THREE.Clock();
 function frame(){
  var t=clock.getElapsedTime();
  sp+=(prog-sp)*.06;hover+=(hoverT-hover)*.08;
  sx+=(mx-sx)*.05;sy+=(my-sy)*.05;
  vel*=.93;var v1=Math.min(vel,1.5);uni.t.value=reduce?0:t*(.7+v1*2);uni.amp.value=.3+hover*.3+v1*.45;
  stops(A,sp,uni.c1.value);stops(B,sp,uni.c2.value);
  var side=mobile?0:2.3;
  blob.position.x=mobile?0:(sp<.05?1.9:Math.cos(sp*Math.PI*5)*side);
  blob.position.y=mobile?1.8-sp*.8:Math.sin(sp*Math.PI*3)*.7;
  blob.scale.setScalar((mobile?.6:1)*(1+hover*.12));
  blob.rotation.y=sp*Math.PI*4+(reduce?0:t*.15);blob.rotation.x=sy*.4;
  rings.rotation.z=reduce?0:t*.1;rings.rotation.x=sp*4;
  pts.rotation.y=sp*1.5+(reduce?0:t*.01);
  cam.fov=50+v1*22;cam.updateProjectionMatrix();cam.position.x=sx*.8;cam.position.y=sy*.5;cam.position.z=6-sp*1.2;cam.lookAt(0,0,0);
  shapes.forEach(function(s){var k=1+v1*8;s.rotation.x+=s.userData.s*k;s.rotation.y+=s.userData.s*1.3*k;s.position.y+=Math.sin(t+s.userData.o)*.004});
  var pb=document.getElementById('pb');
  pb&&(pb.style.transform='scaleX('+sp+')');renderer.render(scene,cam);requestAnimationFrame(frame)}
 frame();

 var chars='!<>-_[]{}=+*^?#ABCXYZ';
 function scramble(el){var txt=el.dataset.t||(el.dataset.t=el.textContent),n=0;var id=setInterval(function(){el.textContent=txt.split('').map(function(c,i){return i<n?c:chars[Math.floor(Math.random()*chars.length)]}).join('');n+=.5;if(n>txt.length){el.textContent=txt;clearInterval(id)}},35)}
 if(!reduce){setTimeout(function(){document.querySelectorAll('[data-s]').forEach(scramble)},1000);}
 
 var cio=new IntersectionObserver(function(es){es.forEach(function(e){if(e.isIntersecting){e.target.classList.add('in');cio.unobserve(e.target)}})},{threshold:.1});
 document.querySelectorAll('.card').forEach(function(c){cio.observe(c)});

 var hio=new IntersectionObserver(function(es){es.forEach(function(e){if(e.isIntersecting){if(!reduce)scramble(e.target);hio.unobserve(e.target)}})},{threshold:.6});
 document.querySelectorAll('h2').forEach(function(h){hio.observe(h)});

 function dot(x,y,sz,col,dx,dy,dur){var d=document.createElement('i');d.className='bp';d.style.cssText='left:'+x+'px;top:'+y+'px;width:'+sz+'px;height:'+sz+'px;background:'+col;document.body.appendChild(d);d.animate([{transform:'translate(-50%,-50%) scale(1)',opacity:1},{transform:'translate(calc(-50% + '+dx+'px),calc(-50% + '+dy+'px)) scale(0)',opacity:0}],{duration:dur,easing:'cubic-bezier(.2,.8,.2,1)}');setTimeout(function(){d.remove()},dur)}
 var cols=['#ffffff','#cccccc','#888888','#dddddd'],lt=0;
 if(!reduce){
  addEventListener('pointermove',function(e){var n=performance.now();if(n-lt>50){lt=n;dot(e.clientX,e.clientY,4,cols[Math.floor(Math.random()*4)],(Math.random()-.5)*15,10+Math.random()*15,500)}});
  addEventListener('pointerdown',function(e){for(var i=0;i<14;i++){var a=Math.random()*6.28,r=40+Math.random()*80;dot(e.clientX,e.clientY,3+Math.random()*5,cols[i%4],Math.cos(a)*r,Math.sin(a)*r,500+Math.random()*300)}})}

 document.querySelectorAll('.btn').forEach(function(b){
  b.addEventListener('pointermove',function(e){var r=b.getBoundingClientRect();b.style.translate=(e.clientX-r.left-r.width/2)*.2+'px '+(e.clientY-r.top-r.height/2)*.3+'px'});
  b.addEventListener('pointerleave',function(){b.style.translate=''});
 });

 addEventListener('keydown',function(e){if(e.key==='w'||e.key==='W')vel=3});

 var bar=document.getElementById('bar'),load=document.getElementById('load');
 requestAnimationFrame(function(){bar.style.width='100%'});
 setTimeout(function(){load.style.opacity=0;setTimeout(function(){load.remove()},800)},1100);
})();
</script>
</body>
</html>