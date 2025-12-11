<template>
  <section id="projects" class="projects-section">
    <!-- subtle decorative vignette / glow -->
    <div class="projects-bg" aria-hidden="true">
      <svg class="grid-svg" viewBox="0 0 800 200" preserveAspectRatio="none" aria-hidden="true">
        <defs>
          <linearGradient id="g1" x1="0" x2="1">
            <stop offset="0" stop-color="#062226" stop-opacity="0.0" />
            <stop offset="1" stop-color="#031018" stop-opacity="0.45" />
          </linearGradient>
        </defs>
        <rect width="800" height="200" fill="url(#g1)"/>
      </svg>
      <div class="neon-orb neon-orb-1"></div>
      <div class="neon-orb neon-orb-2"></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <header class="projects-header">
        <h2 class="title">Projects</h2>
        <p class="subtitle">Selected projects — cards with tech tags, short summaries and links.</p>
      </header>

      <div class="project-grid" role="list">
        <article
          v-for="(p, i) in projects"
          :key="p.title"
          class="project-card reveal"
          role="listitem"
          tabindex="0"
        >
          <div class="card-top">
            <div class="kicker">{{ p.kicker }}</div>
            <div class="year-badge">{{ p.year }}</div>
          </div>

          <h3 class="card-title">{{ p.title }}</h3>
          <p class="card-desc">{{ p.desc }}</p>

          <div class="card-tags">
            <span v-for="tag in p.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>

          <div class="card-actions">
            <a v-if="p.github" :href="p.github" target="_blank" class="btn ghost">GitHub</a>
            <a v-if="p.demo" :href="p.demo" target="_blank" class="btn">Live</a>
          </div>

          <!-- neon rim for glow effect -->
          <div aria-hidden="true" class="neon-rim"></div>
        </article>
      </div>
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from 'vue'

export default {
  name: 'Projects',
  setup() {
    // Projects sourced from Resume_Riteesh.pdf (see source comment above). :contentReference[oaicite:1]{index=1}
    const projects = ref([
      {
        kicker: 'Data Tool',
        title: 'Auto-EDA Tool',
        year: '2025',
        desc: 'Automated exploratory data analysis that generates self-contained HTML reports with summary statistics, distributions, correlations, and outlier analysis. (Dec 2025)',
        tags: ['Python','Streamlit','EDA'],
        github: ''
      },
      {
        kicker: 'ML',
        title: 'System Threat Forecaster',
        year: '2025',
        desc: 'Built machine learning models to predict system threats from log data; evaluated Random Forest and XGBoost classifiers. (Mar–Apr 2025)',
        tags: ['Python','Scikit-learn','Kaggle'],
        github: ''
      },
      {
        kicker: 'Backend / Automation',
        title: 'FastAPI Automation Agent',
        year: '2025',
        desc: 'Developed a REST API agent to automate file operations and script execution, packaged with Docker for consistent deployment. (May–Jun 2025)',
        tags: ['Python','FastAPI','Docker'],
        github: ''
      },
      {
        kicker: 'Analytics',
        title: 'Business Data Management',
        year: '2025',
        desc: 'Analyzed order data to identify regional demand and customer segments; performed segmentation to highlight high-value groups and actionable insights. (Jul–Nov 2025)',
        tags: ['Python','Pandas','Scikit-learn','Excel'],
        github: ''
      }
    ])

    onMounted(() => {
      // intersection observer for reveal
      const els = Array.from(document.querySelectorAll('.reveal'))
      const io = new IntersectionObserver((entries) => {
        entries.forEach(e => {
          if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target) }
        })
      }, { threshold: 0.12 })
      els.forEach(el => io.observe(el))
    })

    return { projects }
  }
}
</script>

<style scoped>
/* ---------- Section base ---------- */
.projects-section{
  position: relative;
  padding: 4.5rem 0 6rem;
  overflow: hidden;
  /* glassy darker band to separate from About */
  background: linear-gradient(180deg, rgba(3,8,12,0.00) 0%, rgba(6,12,18,0.55) 30%, rgba(6,12,18,0.9) 100%);
  border-top: 1px solid rgba(255,255,255,0.02);
  border-bottom: 1px solid rgba(255,255,255,0.02);
}

/* decorative background elements */
.projects-bg { position: absolute; inset: 0; z-index: 2; pointer-events: none; }
.grid-svg { position: absolute; left: 0; top: -8%; width: 100%; height: 40%; opacity: 0.6; filter: blur(10px); }
.neon-orb { position: absolute; width: 260px; height: 260px; border-radius: 50%; filter: blur(60px); opacity: 0.08; }
.neon-orb-1 { right: 6%; top: 8%; background: radial-gradient(circle, rgba(6,182,212,0.2), transparent 45%); }
.neon-orb-2 { left: 8%; bottom: -6%; background: radial-gradient(circle, rgba(139,92,246,0.14), transparent 45%); }

/* ---------- Header ---------- */
.projects-header { margin-bottom: 2rem; color: rgba(230,240,255,0.92); max-width: 880px; }
.title {
  font-size: 2.125rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  margin-bottom: 0.35rem;
  background: linear-gradient(90deg, #06B6D4, #8B5CF6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.subtitle { color: rgba(170,188,200,0.44); margin-top: 0.25rem; }

/* ---------- Grid ---------- */
.project-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.6rem;
}
@media(min-width:900px){
  .project-grid { grid-template-columns: repeat(2, 1fr); gap: 2rem; }
}

/* ---------- Card styles (cyberpunk) ---------- */
.project-card{
  position: relative;
  overflow: visible;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.008));
  border-radius: 14px;
  padding: 1.6rem;
  min-height: 180px;
  box-shadow: 0 28px 70px rgba(0,0,0,0.7);
  border: 1px solid rgba(255,255,255,0.03);
  transition: transform .36s cubic-bezier(.2,.9,.3,1), box-shadow .36s, background .28s;
  isolation: isolate;
  outline: none;
}

/* neon rim using pseudo element (separate layer) */
.project-card .neon-rim {
  position: absolute;
  inset: 0;
  border-radius: 14px;
  pointer-events: none;
  z-index: 0;
  mix-blend-mode: screen;
  transition: opacity .3s ease;
}

/* top row: kicker + year */
.card-top { display:flex; justify-content:space-between; align-items:baseline; gap:1rem; margin-bottom:0.6rem; z-index:1; position:relative; }
.kicker { font-size:12px; color: rgba(170,188,200,0.5); }
.year-badge {
  font-size:13px;
  padding:6px 10px;
  border-radius:999px;
  background: rgba(6,182,212,0.06);
  color: #06B6D4;
  border: 1px solid rgba(6,182,212,0.06);
}

/* title & text */
.card-title {
  font-size:1.25rem;
  font-weight:700;
  margin-top:0.1rem;
  margin-bottom:0.45rem;
  color: rgba(235,245,255,0.95);
  z-index:1;
  position:relative;
}
.card-desc { color: rgba(170,188,200,0.46); line-height:1.6; z-index:1; position:relative; }

/* tags */
.card-tags { display:flex; gap:0.5rem; margin-top:0.85rem; z-index:1; position:relative; }
.tag {
  background: rgba(255,255,255,0.01);
  color: rgba(170,188,200,0.64);
  padding:6px 10px;
  border-radius: 8px;
  font-size:12px;
  border: 1px solid rgba(255,255,255,0.02);
}

/* actions */
.card-actions { margin-top: 1rem; display:flex; gap:0.6rem; z-index:1; position:relative; }
.btn {
  padding:8px 12px;
  border-radius:10px;
  font-size:13px;
  cursor:pointer;
  text-decoration:none;
  display:inline-flex;
  align-items:center;
  gap:0.5rem;
  transition: transform .15s ease, background .2s ease;
  border: 1px solid rgba(255,255,255,0.04);
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.006));
  color: rgba(220,232,244,0.92);
}
.btn.ghost { background: transparent; color: rgba(200,215,230,0.78); border: 1px solid rgba(255,255,255,0.02); }
.btn:hover { transform: translateY(-4px); background: linear-gradient(90deg, rgba(6,182,212,0.06), rgba(139,92,246,0.04)); color: #fff; }

/* hover/focus - stronger neon rim + lift */
.project-card:hover, .project-card:focus {
  transform: translateY(-12px) scale(1.01);
  box-shadow: 0 36px 98px rgba(0,0,0,0.8);
  border-color: rgba(6,182,212,0.08);
}
.project-card:hover .neon-rim,
.project-card:focus .neon-rim {
  opacity: 1;
  background: radial-gradient(circle at 10% 20%, rgba(6,182,212,0.065), transparent 10%),
              radial-gradient(circle at 80% 80%, rgba(139,92,246,0.06), transparent 12%),
              linear-gradient(90deg, rgba(6,182,212,0.02), rgba(139,92,246,0.02));
  box-shadow: 0 0 28px rgba(6,182,212,0.06), inset 0 0 24px rgba(139,92,246,0.02);
}

/* subtle shimmer on the card title for motion */
.card-title::after{
  content: '';
  display:block;
  height:2px;
  width:0%;
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  transition: width .6s ease;
  margin-top:6px;
  border-radius: 2px;
}
.project-card:hover .card-title::after, .project-card:focus .card-title::after {
  width:36%;
}

/* reveal animation (same pattern as hero) */
.reveal { opacity:0; transform: translateY(18px) scale(.995); transition: all .7s cubic-bezier(.2,.9,.3,1); }
.reveal.visible { opacity:1; transform: translateY(0) scale(1); }

/* ensure neon rim not visible until hover */
.project-card .neon-rim { opacity: 0; transition: opacity .28s ease, background .28s ease; }

/* accessibility focus */
.project-card:focus { outline: 2px solid rgba(6,182,212,0.12); outline-offset: 6px; }

/* responsive tweaks */
@media (max-width: 640px) {
  .projects-section { padding: 3rem 0 4rem; }
  .card-top { gap: 0.6rem; }
  .card-title { font-size: 1.08rem; }
}

/* small aesthetic polishing: spacing between grid and footer */
.projects-section::after {
  content: '';
  display:block;
  height: 26px;
}
</style>
