<template>
  <section class="hero-section relative overflow-hidden">
    <!-- animated background artwork (SVG hex ring + particles) -->
    <div class="cyber-bg" aria-hidden="true">
      <!-- rotating hex ring -->
      <svg class="hex-ring" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <g class="hex-rotate" transform="translate(100 100)">
          <circle cx="0" cy="0" r="58" fill="none" stroke="rgba(6,182,212,0.06)" stroke-width="4"/>
          <g class="hex" transform="scale(1)">
            <polygon points="0,-48 41,-24 41,24 0,48 -41,24 -41,-24" fill="none" stroke="#06B6D4" stroke-width="2" stroke-opacity="0.14"/>
            <polygon points="0,-38 33,-19 33,19 0,38 -33,19 -33,-19" fill="none" stroke="#8B5CF6" stroke-width="2" stroke-opacity="0.10"/>
          </g>
        </g>
      </svg>

      <!-- drifting neon particles -->
      <div class="particle p1"></div>
      <div class="particle p2"></div>
      <div class="particle p3"></div>

      <!-- subtle scanline overlay -->
      <div class="scanline" aria-hidden="true"></div>
    </div>

    <!-- content panel -->
    <div class="container mx-auto px-6 relative z-20 max-w-3xl">
      <div class="cyber-panel reveal">
        <div class="panel-left">
          <h1 class="text-5xl md:text-6xl font-extrabold leading-tight">
            Hey — I’m <span class="gradient-text">Riteesh</span>.
          </h1>

          <p class="mt-4 text-lg text-muted max-w-xl">
            I build full-stack applications, ML models, and embedded systems — I like making things that think.
          </p>

          <div class="mt-8 flex gap-4">
            <a href="#projects" class="project-btn">See projects</a>
            <a href="#contact" class="project-btn">Contact</a>
          </div>
        </div>

        <div class="panel-right hidden md:flex items-center justify-center">
          <!-- small neon card / placeholder (optional) -->
          <div class="mini-card accent-outline">
            <div class="kicker text-muted">Core</div>
            <div class="font-semibold gradient-text text-lg mt-1">AI · Systems</div>
            <div class="mt-3 text-sm text-muted">Embedded, ML, Web</div>
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
    // small reveal for the panel
    requestAnimationFrame(() => {
      const el = document.querySelector('.cyber-panel')
      if (el) el.classList.add('visible')
    })
  }
}
</script>

<style scoped>
/* Base layout for hero */
.hero-section {
  min-height: 72vh;
  display: flex;
  align-items: center;
  position: relative;
  padding-top: 3.5rem; /* account for header */
  padding-bottom: 3rem;
}

/* BACKGROUND LAYER */
.cyber-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
  overflow: visible;
  z-index: 5;
}

/* rotating hex SVG */
.hex-ring {
  position: absolute;
  right: 8%;
  top: 4%;
  width: 420px;
  height: 420px;
  transform-origin: center;
  filter: blur(10px) drop-shadow(0 8px 30px rgba(6,182,212,0.06));
  opacity: 0.85;
}
.hex-rotate { transform-origin: center; animation: rotate-slow 26s linear infinite; }
@keyframes rotate-slow { from { transform: rotate(0deg) } to { transform: rotate(360deg) } }

/* drifting neon particles */
.particle {
  position: absolute;
  width: 18px;
  height: 18px;
  border-radius: 50%;
  filter: blur(8px);
  opacity: 0.9;
}
.p1 { right: 28%; top: 22%; background: radial-gradient(circle,#06B6D4 0%, rgba(6,182,212,0.0) 60%); animation: drift-1 12s linear infinite; }
.p2 { right: 6%; top: 60%; width: 24px; height: 24px; background: radial-gradient(circle,#8B5CF6 0%, rgba(139,92,246,0.0) 60%); animation: drift-2 17s linear infinite; }
.p3 { right: 44%; top: 68%; width: 14px; height: 14px; background: radial-gradient(circle,#06B6D4 0%, rgba(6,182,212,0.0) 60%); animation: drift-3 10s linear infinite; }

@keyframes drift-1 { 0% { transform: translateY(0) translateX(0) } 50% { transform: translateY(-28px) translateX(18px) } 100% { transform: translateY(0) translateX(0) } }
@keyframes drift-2 { 0% { transform: translateY(0) translateX(0) } 50% { transform: translateY(-40px) translateX(-28px) } 100% { transform: translateY(0) translateX(0) } }
@keyframes drift-3 { 0% { transform: translateY(0) translateX(0) } 50% { transform: translateY(-18px) translateX(12px) } 100% { transform: translateY(0) translateX(0) } }

/* scanline overlay */
.scanline {
  position: absolute;
  inset: 0;
  background-image: linear-gradient(transparent 92%, rgba(255,255,255,0.02) 93%, transparent 100%);
  background-size: 100% 28px;
  opacity: 0.06;
  animation: scan 6s linear infinite;
}
@keyframes scan { 0% { background-position: 0 0 } 100% { background-position: 0 28px } }

/* CYBER PANEL (glass card) */
.cyber-panel {
  display: flex;
  gap: 2rem;
  align-items: stretch;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  border: 1px solid rgba(255,255,255,0.04);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  padding: 2rem;
  border-radius: 14px;
  box-shadow: 0 28px 60px rgba(0,0,0,0.7);
  transform-origin: center;
  opacity: 0;
  transform: translateY(18px) scale(0.995);
  transition: all .7s cubic-bezier(.2,.9,.3,1);
}

/* reveal visible */
.cyber-panel.visible { opacity: 1; transform: translateY(0) scale(1); }

/* left and right columns inside panel */
.panel-left { flex: 1 1 60%; min-width: 0; }
.panel-right { flex: 0 0 220px; }

/* mini-card on right */
.mini-card {
  width: 160px;
  padding: 0.9rem;
  border-radius: 12px;
  text-align: center;
  background: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
  border: 1px solid rgba(255,255,255,0.04);
  box-shadow: 0 14px 40px rgba(2,6,23,0.6);
}

/* accent outline (neon) */
.accent-outline {
  box-shadow: 0 0 28px rgba(6,182,212,0.06), inset 0 0 40px rgba(139,92,246,0.02);
  border: 1px solid rgba(6,182,212,0.06);
}

/* text adjustments */
.gradient-text {
  background: linear-gradient(90deg, #06B6D4, #8B5CF6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* make sure hero never causes horizontal scroll */
.hero-section, .cyber-bg {
  max-width: 100%;
  overflow-x: hidden;
}

/* responsive tweaks */
@media (max-width: 900px) {
  .hex-ring { width: 300px; height: 300px; right: -10%; top: -8%; filter: blur(14px); }
  .panel-right { display: none; }
  .cyber-panel { padding: 1.25rem; border-radius: 12px; gap: 1rem; }
  .panel-left h1 { font-size: 2rem; }
}

/* small accessibility / focus */
a:focus { outline: 3px solid rgba(6,182,212,0.14); outline-offset: 4px; border-radius: 8px; }
</style>
