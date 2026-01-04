<template>
  <section class="hero-section relative overflow-hidden">
    <!-- Animated cyberpunk background -->
    <div class="cyber-bg" aria-hidden="true">
      <!-- Rotating hex ring -->
      <svg class="hex-ring" viewBox="0 0 200 200">
        <g class="hex-rotate" transform="translate(100 100)">
          <circle cx="0" cy="0" r="58" fill="none"
            stroke="rgba(6,182,212,0.06)" stroke-width="4"/>
          <polygon points="0,-48 41,-24 41,24 0,48 -41,24 -41,-24"
            fill="none" stroke="#06B6D4" stroke-opacity="0.14" stroke-width="2"/>
          <polygon points="0,-38 33,-19 33,19 0,38 -33,19 -33,-19"
            fill="none" stroke="#8B5CF6" stroke-opacity="0.10" stroke-width="2"/>
        </g>
      </svg>

      <!-- drifting neon particles -->
      <div class="particle p1"></div>
      <div class="particle p2"></div>
      <div class="particle p3"></div>

      <!-- scanline -->
      <div class="scanline"></div>
    </div>

    <!-- Content -->
    <div class="container mx-auto px-6 relative z-20 max-w-5xl">
      <div class="cyber-panel reveal">
        <div class="panel-left">
          <h1 class="title">
            Hey, I'm <span class="gradient-text">Riteesh</span>.
          </h1>

          <p class="subtitle">
            I work at the intersection of software engineering and AI — building scalable apps, practical ML models.
          </p>

          <div class="mt-8 flex gap-4">
            <a href="#projects" class="hero-btn">See projects</a>
            <a href="#contact" class="hero-btn">Contact</a>
          </div>

          <!-- Small badges -->

        </div>

        <!-- Right decorative glow -->
        <div class="panel-right hidden md:flex">
          <div class="decor">
            <div class="orb"></div>
            <div class="line"></div>
            <div class="orb alt"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Hero",
  mounted() {
    requestAnimationFrame(() => {
      document.querySelector(".cyber-panel")?.classList.add("visible")
    })
  }
}
</script>

<style scoped>
/* ---------- LAYOUT ---------- */
.hero-section {
  min-height: 75vh;
  display: flex;
  align-items: center;
  padding-top: 3rem;
  padding-bottom: 3rem;
  overflow-x: hidden;
}

/* ---------- BACKGROUND ELEMENTS ---------- */
.cyber-bg { position: absolute; inset: 0; pointer-events: none; }

/* Hex ring */
.hex-ring {
  position: absolute;
  right: 10%;
  top: 4%;
  width: 420px;
  height: 420px;
  opacity: 0.85;
  filter: blur(10px);
}
.hex-rotate {
  animation: spin 26s linear infinite;
}
@keyframes spin { from { transform: rotate(0deg);} to { transform: rotate(360deg);} }

/* Particles */
.particle {
  position: absolute;
  border-radius: 50%;
  filter: blur(8px);
  opacity: 0.8;
}
.p1 { right: 30%; top: 25%; width: 18px; height: 18px;
  background: radial-gradient(circle,#06B6D4 0%, transparent 60%);
  animation: drift1 12s infinite linear;
}
.p2 { right: 10%; top: 60%; width: 24px; height: 24px;
  background: radial-gradient(circle,#8B5CF6 0%, transparent 60%);
  animation: drift2 16s infinite linear;
}
.p3 { right: 45%; top: 70%; width: 14px; height: 14px;
  background: radial-gradient(circle,#06B6D4 0%, transparent 60%);
  animation: drift3 10s infinite linear;
}

@keyframes drift1 {50% { transform: translate(20px,-28px);} }
@keyframes drift2 {50% { transform: translate(-30px,-40px);} }
@keyframes drift3 {50% { transform: translate(14px,-18px);} }

/* Scanline */
.scanline {
  position: absolute;
  inset: 0;
  background-image: linear-gradient(transparent 92%, rgba(255,255,255,0.03) 95%, transparent 100%);
  background-size: 100% 28px;
  opacity: 0.06;
  animation: scan 6s linear infinite;
}
@keyframes scan { 100% { background-position: 0 28px; } }

/* ---------- CONTENT PANEL (NO CARD) ---------- */
.cyber-panel {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  opacity: 0;
  transform: translateY(22px);
  transition: all .7s cubic-bezier(.2,.9,.3,1);
  background: none !important;
  border: none !important;
  box-shadow: none !important;
  backdrop-filter: none !important;
}
.cyber-panel.visible {
  opacity: 1;
  transform: translateY(0);
}

@media (min-width: 900px) {
  .cyber-panel {
    grid-template-columns: 1fr 260px;
  }
}

/* ---------- TEXT ---------- */
.title {
  font-size: 3.8rem;
  line-height: 1.05;
  font-weight: 800;
  color: #E9F0FF;
}
.gradient-text {
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.subtitle {
  margin-top: 1rem;
  color: rgba(200,215,230,0.70);
  font-size: 1.25rem;
  max-width: 650px;
}

/* ---------- BUTTONS ---------- */
.hero-btn {
  border: 1px solid rgba(255,255,255,0.04);
  padding: 10px 16px;
  border-radius: 10px;
  background: rgba(255,255,255,0.02);
  color: #E9F0FF;
  transition: .18s ease;
}
.hero-btn:hover {
  transform: translateY(-4px);
  box-shadow: 0 18px 40px rgba(6,182,212,0.06);
}

/* ---------- BADGES ---------- */
.inline-badges {
  margin-top: 18px;
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}
.badge {
  padding: 6px 12px;
  border-radius: 999px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.04);
  color: rgba(210,225,240,0.85);
  font-size: 13px;
}

/* ---------- DECOR RIGHT SIDE ---------- */
.panel-right { display:flex; align-items:center; justify-content:center; }
.decor { display:flex; flex-direction:column; align-items:center; gap:14px; }
.orb {
  width: 60px; height: 60px;
  border-radius: 50%;
  background: radial-gradient(circle,#06B6D4, transparent);
  opacity: 0.1;
  filter: blur(18px);
}
.orb.alt { background: radial-gradient(circle,#8B5CF6, transparent); }
.line {
  width: 110px;
  height: 6px;
  border-radius: 999px;
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  filter: blur(6px);
  opacity: 0.06;
}

/* ---------- MOBILE ---------- */
@media (max-width: 900px) {
  .title { font-size: 2.4rem; }
  .panel-right { display: none; }
}
</style>
