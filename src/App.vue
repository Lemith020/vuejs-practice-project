<script setup>
import { ref } from 'vue'
import profilePhoto from './assets/profile.png'

const isDark = ref(false)

const skills = [
  'Vue.js',
  'JavaScript',
  'React Native',
  'Node.js',
  'PostgreSQL',
  'Git & GitHub',
]

const interests = [
  { icon: '💻', title: 'Web Development' },
  { icon: '📱', title: 'Mobile Applications' },
  { icon: '⚙️', title: 'IoT & Embedded Systems' },
]
</script>

<template>
  <main class="page" :class="{ dark: isDark }">
    <!-- Background decorations -->
    <div class="glow glow-one" aria-hidden="true"></div>
    <div class="glow glow-two" aria-hidden="true"></div>

    <div class="page-content">
      <header class="topbar">
        <span class="brand">
          <span class="brand-dot"></span>
          My little corner
        </span>

        <button
          class="theme-button"
          type="button"
          :aria-pressed="isDark"
          @click="isDark = !isDark"
        >
          {{ isDark ? '☀️ Light mode' : '🌙 Dark mode' }}
        </button>
      </header>

      <article class="profile-card">
        <div class="cover">
          <span class="cover-label">LEARN. BUILD. REPEAT.</span>

          <span class="cover-symbol" aria-hidden="true">
            &lt;/&gt;
          </span>
        </div>

        <div class="card-content">
          <div class="profile-heading">
            <div class="avatar-frame">
              <img
                :src="profilePhoto"
                alt="Lemith's profile photo"
                class="avatar"
              />
            </div>

            <span class="status">
              <span class="status-dot"></span>
              Open to learning
            </span>
          </div>

          <div class="intro">
            <p class="eyebrow">HELLO THERE, I'M</p>

            <h1>Lemith <span class="wave">👋</span></h1>

            <p class="role">Software Engineering Undergraduate</p>

            <p class="bio">
              Turning curiosity into code. I enjoy building useful web
              and mobile applications, exploring new technologies,
              and learning something new every day.
            </p>
          </div>

          <div class="details">
            <div class="detail-item">
              <span class="detail-icon" aria-hidden="true">🎓</span>

              <div>
                <span class="detail-label">UNIVERSITY</span>
                <p>University of Kelaniya</p>
              </div>
            </div>

            <div class="detail-item">
              <span class="detail-icon" aria-hidden="true">📍</span>

              <div>
                <span class="detail-label">BASED IN</span>
                <p>Matara, Sri Lanka</p>
              </div>
            </div>
          </div>

          <section class="section">
            <h2>My toolbox <span>🛠️</span></h2>

            <div class="skills">
              <span
                v-for="skill in skills"
                :key="skill"
                class="skill"
              >
                {{ skill }}
              </span>
            </div>
          </section>

          <section class="section">
            <h2>What excites me <span>✨</span></h2>

            <div class="interests">
              <div
                v-for="interest in interests"
                :key="interest.title"
                class="interest"
              >
                <span class="interest-icon" aria-hidden="true">
                  {{ interest.icon }}
                </span>

                <span>{{ interest.title }}</span>
              </div>
            </div>
          </section>

          <div class="learning-note">
            <span aria-hidden="true">🌱</span>
            <p>Currently exploring <strong>Vue.js</strong>, one component at a time.</p>
          </div>

          <a
            class="github-button"
            href="https://github.com/Lemith020"
            target="_blank"
            rel="noopener noreferrer"
          >
            Explore my GitHub
            <span aria-hidden="true">↗</span>
          </a>

          <p class="card-footer">
            A little progress, every single day.
          </p>
        </div>
      </article>

      <footer class="page-footer">
        Built with Vue.js <span>•</span> Made with curiosity
      </footer>
    </div>
  </main>
</template>

<!-- Global styles: browser default spacing ඉවත් කරනවා -->
<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: 'Segoe UI', Arial, sans-serif;
}

button,
a {
  -webkit-tap-highlight-color: transparent;
}

button {
  font: inherit;
}
</style>

<style scoped>
.page {
  --background: #f3f5fc;
  --card: #ffffff;
  --text: #17213b;
  --muted: #68758d;
  --border: #e8ecf5;
  --surface: #f7f8fc;
  --accent: #6554df;
  --chip-background: #efedff;
  --chip-text: #5945c5;

  min-height: 100vh;
  padding: 30px 20px 24px;
  position: relative;
  isolation: isolate;
  overflow: hidden;
  color: var(--text);
  background: var(--background);
  transition: background-color 0.35s ease, color 0.35s ease;
}

.page.dark {
  --background: #101322;
  --card: #1b2033;
  --text: #f2f4ff;
  --muted: #adb8d1;
  --border: #30374e;
  --surface: #232a40;
  --accent: #b1a5ff;
  --chip-background: #322d50;
  --chip-text: #d1c9ff;
}

.page-content {
  position: relative;
  z-index: 1;
  max-width: 680px;
  margin: 0 auto;
}

.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 28px;
}

.brand {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  font-size: 13px;
  font-weight: 650;
  color: var(--muted);
}

.brand-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--accent);
}

.theme-button {
  padding: 10px 14px;
  border: 1px solid var(--border);
  border-radius: 30px;
  background: var(--card);
  color: var(--text);
  cursor: pointer;
  font-size: 12px;
  font-weight: 600;
  transition: transform 0.2s ease;
}

.theme-button:hover {
  transform: translateY(-2px);
}

.profile-card {
  overflow: hidden;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 28px;
  box-shadow: 0 24px 70px rgba(30, 30, 80, 0.09);
  animation: enter 0.7s ease both;
  transition: background-color 0.35s ease, border-color 0.35s ease;
}

.cover {
  height: 150px;
  padding: 25px 30px;
  position: relative;
  overflow: hidden;
  background: linear-gradient(120deg, #6050dc, #8f6fe9 55%, #b391ee);
}

.cover::after {
  content: '';
  position: absolute;
  width: 230px;
  height: 230px;
  right: -30px;
  top: -100px;
  border: 36px solid rgba(255, 255, 255, 0.12);
  border-radius: 50%;
}

.cover-label {
  color: #ffffff;
  font-size: 10px;
  letter-spacing: 3px;
  font-weight: 700;
}

.cover-symbol {
  position: absolute;
  right: 36px;
  bottom: 12px;
  color: rgba(255, 255, 255, 0.35);
  font-size: 66px;
  font-weight: 800;
  transform: rotate(-10deg);
}

.card-content {
  padding: 0 34px 26px;
}

.profile-heading {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 14px;
  position: relative;
  margin-top: -48px;
  margin-bottom: 24px;
}

.avatar-frame {
  flex-shrink: 0;
  width: 116px;
  height: 116px;
  padding: 5px;
  background: var(--card);
  border-radius: 30px;
  transform: rotate(-4deg);
  box-shadow: 0 8px 22px rgba(25, 28, 60, 0.15);
  transition: transform 0.3s ease;
}

.avatar-frame:hover {
  transform: rotate(0deg) scale(1.04);
}

.avatar {
  display: block;
  width: 100%;
  height: 100%;
  border-radius: 25px;
  object-fit: cover;
  object-position: center;
}

.status {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 8px 11px;
  margin-bottom: 5px;
  border-radius: 20px;
  background: var(--surface);
  color: var(--text);
  font-size: 11px;
  font-weight: 600;
}

.status-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #22a874;
  animation: pulse 2s ease-out infinite;
}

.eyebrow {
  margin: 0 0 7px;
  color: var(--accent);
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 2px;
}

h1 {
  margin: 0;
  font-size: clamp(32px, 7vw, 42px);
  line-height: 1.2;
  letter-spacing: -1.5px;
}

.wave {
  display: inline-block;
  font-size: 30px;
  transform-origin: 70% 75%;
  animation: wave 2s ease 0.6s;
}

.role {
  margin: 10px 0 0;
  color: var(--accent);
  font-size: 14px;
  font-weight: 650;
}

.bio {
  margin: 16px 0 23px;
  color: var(--muted);
  font-size: 14px;
  line-height: 1.85;
}

.details {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
  padding: 17px;
  border: 1px solid var(--border);
  border-radius: 16px;
  background: var(--surface);
}

.detail-item {
  display: flex;
  align-items: center;
  gap: 10px;
}

.detail-icon {
  font-size: 23px;
}

.detail-label {
  color: var(--muted);
  font-size: 9px;
  font-weight: 700;
  letter-spacing: 1px;
}

.detail-item p {
  margin: 4px 0 0;
  font-size: 12px;
  font-weight: 650;
  line-height: 1.5;
}

.section {
  margin-top: 25px;
}

h2 {
  margin: 0 0 13px;
  font-size: 14px;
  font-weight: 750;
}

h2 span {
  margin-left: 5px;
}

.skills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.skill {
  padding: 8px 12px;
  border-radius: 9px;
  background: var(--chip-background);
  color: var(--chip-text);
  font-size: 11px;
  font-weight: 650;
  transition: transform 0.2s ease;
}

.skill:hover {
  transform: translateY(-3px);
}

.interests {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 9px;
}

.interest {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 9px;
  padding: 15px 12px;
  border: 1px solid var(--border);
  border-radius: 13px;
  font-size: 11px;
  font-weight: 600;
  line-height: 1.5;
  transition: transform 0.2s ease, background-color 0.2s ease;
}

.interest:hover {
  transform: translateY(-4px);
  background: var(--surface);
}

.interest-icon {
  font-size: 23px;
}

.learning-note {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 24px;
  padding: 13px 14px;
  border-radius: 12px;
  background: var(--surface);
}

.learning-note p {
  margin: 0;
  color: var(--muted);
  font-size: 12px;
  line-height: 1.7;
}

.learning-note strong {
  color: var(--accent);
}

.github-button {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 22px;
  padding: 15px 19px;
  border-radius: 13px;
  background: linear-gradient(110deg, #6554df, #8564e2);
  color: white;
  text-decoration: none;
  font-size: 13px;
  font-weight: 650;
  box-shadow: 0 6px 18px rgba(101, 84, 223, 0.22);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.github-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(101, 84, 223, 0.32);
}

.github-button span {
  font-size: 20px;
}

.theme-button:focus-visible,
.github-button:focus-visible {
  outline: 3px solid var(--accent);
  outline-offset: 4px;
}

.card-footer {
  margin: 18px 0 0;
  text-align: center;
  color: var(--muted);
  font-size: 11px;
}

.page-footer {
  margin-top: 22px;
  text-align: center;
  color: var(--muted);
  font-size: 11px;
}

.page-footer span {
  margin: 0 8px;
  color: var(--accent);
}

.glow {
  position: absolute;
  z-index: 0;
  width: 340px;
  height: 340px;
  border-radius: 50%;
  filter: blur(65px);
  opacity: 0.2;
  pointer-events: none;
}

.glow-one {
  top: 40px;
  left: -150px;
  background: #9a7cf5;
}

.glow-two {
  bottom: 30px;
  right: -150px;
  background: #6cbde8;
}

@keyframes enter {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(34, 168, 116, 0.3);
  }
  100% {
    box-shadow: 0 0 0 7px rgba(34, 168, 116, 0);
  }
}

@keyframes wave {
  0%, 100% { transform: rotate(0deg); }
  20%, 60% { transform: rotate(18deg); }
  40%, 80% { transform: rotate(-8deg); }
}

@media (max-width: 480px) {
  .page {
    padding: 20px 14px;
  }

  .brand {
    font-size: 11px;
  }

  .theme-button {
    padding: 9px 11px;
    font-size: 11px;
  }

  .card-content {
    padding: 0 20px 24px;
  }

  .cover {
    height: 130px;
    padding: 22px;
  }

  .avatar-frame {
    width: 100px;
    height: 100px;
  }

  .status {
    padding: 7px 9px;
    font-size: 10px;
  }

  .details {
    grid-template-columns: 1fr;
  }

  .interests {
    grid-template-columns: 1fr;
  }

  .interest {
    flex-direction: row;
    align-items: center;
  }
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation: none !important;
    transition: none !important;
  }
}
</style>