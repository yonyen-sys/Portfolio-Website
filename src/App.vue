<template>
  <div id="app" class="app-shell">
    <header class="hero" id="home">
      <div class="hero-copy">
        <p class="eyebrow">Hello, I’m</p>
        <h1>Yen Yon</h1>
        <p class="hero-title">Trainer at PNC & Coding Teacher</p>
        <p class="hero-text">
          I teach JavaScript, PHP, and web development from fundamentals to real-world project implementation.
          My work focuses on helping students build practical applications and succeed with client-side technologies.
        </p>
        <div class="hero-actions">
          <a class="button button-primary" href="#projects">View Projects</a>
          <DownloadPdf :target-ref="pdfContentRef" />
        </div>
      </div>
      <div class="hero-image" aria-label="Profile photo">
        <img :src="profileSrc" alt="Yen Yon profile photo" class="profile-photo" />
      </div>
    </header>

    <main ref="pageContent" class="page-content">
      <section class="section about" id="about">
        <div class="section-header">
          <span>About me</span>
          <h2>Professional Summary</h2>
        </div>
        <p>
          My name is Yon Yen. I am a trainer at PNC and a coding teacher specializing in JavaScript and PHP.
          I help students master programming from the fundamentals to advanced concepts, and I enjoy guiding them to build real-world web projects.
        </p>
      </section>

      <section class="section experience" id="experience">
        <div class="section-header">
          <span>Experience</span>
          <h2>Career Highlights</h2>
        </div>
        <div class="timeline">
          <article class="timeline-item">
            <h3>Web Trainer at PNC</h3>
            <span>Jan 2023 - Dec 2023</span>
            <ul>
              <li>Designed lesson plans and managed course delivery.</li>
              <li>Taught HTML, CSS, JavaScript, Node.js, PHP, Laravel, OOP, Vue.js, and algorithms.</li>
              <li>Guided students through real-world project development.</li>
            </ul>
          </article>
          <article class="timeline-item">
            <h3>Back-End Developer at Godingate</h3>
            <span>Aug 2020 - Dec 2020</span>
            <ul>
              <li>Built APIs for websites using Laravel, MySQL, and Postman.</li>
              <li>Integrated APIs with POS and admin systems using Vue.js and Laravel.</li>
              <li>Developed mobile app APIs with Laravel or CodeIgniter.</li>
              <li>Built POS and admin interfaces with Vue.js, Laravel, and Bootstrap.</li>
            </ul>
          </article>
          <article class="timeline-item">
            <h3>Back-End Developer at Mangobyte</h3>
            <span>Aug 2020 - Dec 2020</span>
            <ul>
              <li>Built admin and POS interfaces with Nuxt.js.</li>
              <li>Integrated APIs for admin and POS systems using Nuxt.js and TypeScript.</li>
              <li>Built admin/POS APIs with NestJS, TypeORM, and TypeScript.</li>
            </ul>
          </article>
          <article class="timeline-item">
            <h3>Projects Delivered</h3>
            <span>Aug 2020 - Dec 2023</span>
            <ul>
              <li>Ucare Pharmacy App</li>
              <li>Kenoir App</li>
              <li>APSOR, MBA, B2B, Nokor App</li>
              <li>Save Children System</li>
            </ul>
          </article>
        </div>
      </section>

      <section class="section education" id="education">
        <div class="section-header">
          <span>Education</span>
          <h2>Academic Background</h2>
        </div>
        <div class="education-grid">
          <div class="education-card">
            <h3>Bachelor Degree</h3>
            <p>AEU Cambodia</p>
            <span>Jan 2023 - Dec 2025</span>
          </div>
          <div class="education-card">
            <h3>Associate Degree</h3>
            <p>Passerelles numériques</p>
            <span>Jan 2018 - Dec 2020</span>
          </div>
        </div>
      </section>

      <Skills />
      <Projects />
      <Contact />
    </main>

    <div id="pdfContent" class="resume-export" ref="pdfContent">
      <div class="resume-layout">
        <aside class="resume-sidebar">
          <div class="sidebar-profile">
            <div class="sidebar-photo">
              <img :src="profileSrc" alt="Yen Yon profile photo" />
            </div>
            <h1>Yen Yen</h1>
            <p class="sidebar-role">Trainer at PNC & Coding Teacher</p>
          </div>

          <div class="sidebar-section">
            <h3>Profile</h3>
            <p>Passionate trainer and coding instructor with a strong focus on JavaScript, PHP, and practical web application development.</p>
          </div>

          <div class="sidebar-section">
            <h3>Contact</h3>
            <p>yon.yen@passerellesnumeriques.org</p>
            <p>086750534</p>
            <p>Phnom Penh, Cambodia</p>
          </div>

          <div class="sidebar-section">
            <h3>Skills</h3>
            <ul>
              <li>JavaScript</li>
              <li>PHP & Laravel</li>
              <li>Vue.js / Nuxt.js</li>
              <li>Responsive UI</li>
            </ul>
          </div>

          <div class="sidebar-section">
            <h3>Languages</h3>
            <ul>
              <li>Khmer — Native</li>
              <li>English — Intermediate</li>
            </ul>
          </div>
        </aside>

        <main class="resume-main">
          <section class="resume-block resume-summary">
            <div class="section-label">Summary</div>
            <p>Experienced trainer and developer who helps students learn real-world web development through practical, project-based courses and clear technical guidance.</p>
          </section>

          <section class="resume-block">
            <div class="section-label">Experience</div>
            <article class="resume-item">
              <h2>Web Trainer at PNC</h2>
              <p class="meta">Jan 2023 - Dec 2023</p>
              <ul>
                <li>Designed lesson plans and managed course delivery.</li>
                <li>Taught HTML, CSS, JavaScript, Node.js, PHP, Laravel, OOP, Vue.js, and algorithms.</li>
                <li>Guided students through real-world project development.</li>
              </ul>
            </article>
            <article class="resume-item">
              <h2>Back-End Developer at Godingate</h2>
              <p class="meta">Aug 2020 - Dec 2020</p>
              <ul>
                <li>Built APIs for websites using Laravel, MySQL, and Postman.</li>
                <li>Integrated APIs with POS and admin systems using Vue.js and Laravel.</li>
                <li>Developed mobile app APIs with Laravel or CodeIgniter.</li>
              </ul>
            </article>
            <article class="resume-item">
              <h2>Back-End Developer at Mangobyte</h2>
              <p class="meta">Aug 2020 - Dec 2020</p>
              <ul>
                <li>Built admin and POS interfaces with Nuxt.js.</li>
                <li>Integrated APIs for admin and POS systems using Nuxt.js and TypeScript.</li>
                <li>Built admin/POS APIs with NestJS, TypeORM, and TypeScript.</li>
              </ul>
            </article>
          </section>

          <section class="resume-block">
            <div class="section-label">Education</div>
            <article class="resume-item">
              <h2>Bachelor Degree</h2>
              <p class="meta">AEU Cambodia | Jan 2023 - Dec 2025</p>
            </article>
            <article class="resume-item">
              <h2>Associate Degree</h2>
              <p class="meta">Passerelles numériques | Jan 2018 - Dec 2020</p>
            </article>
          </section>

          <section class="resume-block">
            <div class="section-label">Projects</div>
            <ul class="project-list">
              <li>Alumini Media - tolakh.site/login</li>
              <li>អាណាចក្រភំ្នស្វាយ - finall-vc1.vercel.app</li>
              <li>CHONG CHOUL - chongchoul.online</li>
              <li>គម្ពី-ELibrary - e-library.app</li>
            </ul>
          </section>
        </main>
      </div>
    </div>

    <footer class="footer">
      <p>Built with Vue 2, PWA support, and client-side PDF export.</p>
    </footer>
  </div>
</template>

<script>
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';
import DownloadPdf from './components/DownloadPdf.vue';

export default {
  name: 'App',
  components: {
    Skills,
    Projects,
    Contact,
    DownloadPdf
  },
  data() {
    return {
      pdfContentRef: 'pdfContent'
    };
  },
  computed: {
    profileSrc() {
      return `${process.env.BASE_URL}photo_2025-04-25_20-14-07.jpg`;
    }
  }
};
</script>

<style>
:root {
  --bg: #eef7ff;
  --surface: rgba(255, 255, 255, 0.92);
  --text: #0f172a;
  --muted: #475569;
  --primary: #2563eb;
  --primary-dark: #1d4ed8;
  --border: rgba(37, 99, 235, 0.16);
  --shadow: 0 28px 90px rgba(15, 23, 42, 0.08);
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  min-height: 100vh;
  font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  background: radial-gradient(circle at top left, rgba(37, 99, 235, 0.16), transparent 24%),
    radial-gradient(circle at bottom right, rgba(59, 130, 246, 0.12), transparent 22%),
    #eef7ff;
  color: var(--text);
}

.app-shell {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.resume-export {
  position: absolute;
  left: -9999px;
  top: 0;
  width: 920px;
  min-height: 1260px;
  background: #ffffff;
  color: #0f172a;
  border-radius: 28px;
  box-shadow: 0 28px 90px rgba(15, 23, 42, 0.08);
  opacity: 1;
  pointer-events: none;
  z-index: -1;
}

.resume-layout {
  display: grid;
  grid-template-columns: 320px 1fr;
  min-height: 100%;
  font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}

.resume-sidebar {
  background: #111827;
  color: #f9fafb;
  padding: 36px 28px;
  display: flex;
  flex-direction: column;
  gap: 28px;
}

.sidebar-profile {
  text-align: center;
}

.sidebar-photo {
  width: 160px;
  height: 160px;
  margin: 0 auto 20px;
  border-radius: 50%;
  overflow: hidden;
  border: 5px solid #dc2626;
}

.sidebar-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.sidebar-profile h1 {
  margin: 0;
  font-size: 2rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.sidebar-role {
  margin: 0.75rem 0 0;
  font-size: 0.95rem;
  letter-spacing: 0.12em;
  color: #cbd5e1;
}

.sidebar-section {
  background: rgba(255, 255, 255, 0.06);
  border-radius: 20px;
  padding: 18px 18px 20px;
}

.sidebar-section h3 {
  margin: 0 0 14px;
  padding: 0.45rem 0.9rem;
  display: inline-block;
  background: #dc2626;
  color: #ffffff;
  font-size: 0.85rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  border-radius: 999px;
}

.sidebar-section p,
.sidebar-section li {
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.7;
  color: #e5e7eb;
}

.sidebar-section ul {
  padding-left: 1rem;
  margin: 0;
}

.sidebar-section li {
  margin-bottom: 0.65rem;
}

.resume-main {
  padding: 44px 44px 52px;
}

.resume-block {
  margin-bottom: 32px;
}

.section-label {
  display: inline-block;
  background: #dc2626;
  color: white;
  font-size: 0.85rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  padding: 0.55rem 1rem;
  border-radius: 999px;
  margin-bottom: 18px;
}

.resume-summary p,
.resume-item p,
.resume-item li,
.project-list li {
  color: #4b5563;
}

.resume-summary p {
  margin: 0;
  line-height: 1.8;
}

.resume-item {
  margin-bottom: 26px;
}

.resume-item h2 {
  margin: 0 0 6px;
  font-size: 1.05rem;
}

.meta {
  margin: 0 0 10px;
  font-size: 0.95rem;
  color: #6b7280;
}

.resume-item ul {
  margin: 0;
  padding-left: 1.2rem;
}

.resume-item li {
  margin-bottom: 0.65rem;
}

.project-list {
  margin: 0;
  padding-left: 1.2rem;
}

.project-list li {
  margin-bottom: 0.7rem;
}

.hero {
  position: relative;
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 3rem;
  align-items: center;
  padding: 4rem 2rem 2rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.96), rgba(240, 249, 255, 0.95));
  border-radius: 40px;
  box-shadow: var(--shadow);
  border: 1px solid rgba(37, 99, 235, 0.12);
}

.hero::before {
  content: '';
  position: absolute;
  width: 320px;
  height: 320px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(37, 99, 235, 0.12), transparent 55%);
  top: -80px;
  right: -80px;
  pointer-events: none;
}

.hero-copy {
  max-width: 640px;
}

.hero h1 {
  font-size: clamp(2.5rem, 4vw, 4rem);
  margin: 0.4rem 0 0.8rem;
}

.eyebrow,
.hero-title {
  text-transform: uppercase;
  letter-spacing: 0.24em;
  font-size: 0.85rem;
  color: var(--primary);
  font-weight: 700;
}

.hero-text {
  font-size: 1.05rem;
  line-height: 1.9;
  color: var(--muted);
  margin: 1.2rem 0 1.8rem;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.95rem 1.5rem;
  border-radius: 999px;
  text-decoration: none;
  font-weight: 700;
  transition: transform 0.2s ease, box-shadow 0.2s ease, background-color 0.2s ease;
  box-shadow: 0 18px 40px rgba(37, 99, 235, 0.14);
}

.button:hover {
  transform: translateY(-2px);
  box-shadow: 0 22px 45px rgba(37, 99, 235, 0.18);
}

.button-primary {
  background: linear-gradient(135deg, #2563eb 0%, #3b82f6 100%);
  color: white;
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1.5rem;
  border-radius: 32px;
  background: linear-gradient(180deg, #edf6ff 0%, #dbeafe 100%);
}

.profile-photo,
.avatar {
  width: min(320px, 100%);
  aspect-ratio: 1 / 1;
  border-radius: 32px;
  display: grid;
  place-items: center;
  box-shadow: var(--shadow);
}

.profile-photo {
  object-fit: cover;
  border-radius: 32px;
}

.avatar {
  background: linear-gradient(180deg, #2563eb 0%, #60a5fa 100%);
  color: white;
  font-size: clamp(3rem, 6vw, 5rem);
  font-weight: 800;
}

.page-content {
  width: min(1100px, 100%);
  margin: 0 auto;
  padding: 0 2rem 4rem;
}

.section {
  background: rgba(255, 255, 255, 0.95);
  border: 1px solid rgba(15, 23, 42, 0.08);
  border-radius: 28px;
  padding: 2rem;
  margin-top: 2rem;
  box-shadow: var(--shadow);
}

.timeline {
  display: grid;
  gap: 1rem;
}

.timeline-item {
  padding: 1.5rem;
  border-radius: 24px;
  background: #ffffff;
  border-left: 4px solid rgba(37, 99, 235, 0.8);
  box-shadow: 0 14px 30px rgba(15, 23, 42, 0.06);
}

.timeline-item h3 {
  margin: 0 0 0.35rem;
}

.timeline-item span {
  display: inline-block;
  margin-bottom: 1rem;
  color: var(--muted);
  font-size: 0.95rem;
}

.timeline-item ul {
  margin: 0;
  padding-left: 1.2rem;
  color: var(--muted);
}

.timeline-item li {
  margin-bottom: 0.6rem;
}

.education-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(220px, 1fr));
  gap: 1rem;
}

.education-card {
  padding: 1.5rem;
  border-radius: 24px;
  background: #ffffff;
  border: 1px solid rgba(15, 23, 42, 0.08);
  box-shadow: 0 18px 32px rgba(15, 23, 42, 0.05);
}

.education-card h3 {
  margin: 0 0 0.5rem;
}

.education-card span {
  color: var(--muted);
  font-size: 0.95rem;
}

.section-header {
  display: flex;
  align-items: baseline;
  gap: 1rem;
  margin-bottom: 1.2rem;
}

.section-header span {
  color: var(--primary);
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  font-size: 0.8rem;
}

.section-header h2 {
  margin: 0;
  font-size: 1.75rem;
}

.footer {
  margin-top: auto;
  padding: 2rem;
  text-align: center;
  color: var(--muted);
  font-size: 0.95rem;
}

@media (max-width: 900px) {
  .hero {
    grid-template-columns: 1fr;
    padding: 3rem 1.25rem 1.75rem;
  }

  .hero-image {
    padding-top: 1rem;
  }
}

@media (max-width: 660px) {
  .hero {
    padding: 2rem 1rem 1.5rem;
  }

  .hero-actions {
    flex-direction: column;
    align-items: stretch;
  }

  .page-content {
    padding: 0 1rem 3rem;
  }
}
</style>
