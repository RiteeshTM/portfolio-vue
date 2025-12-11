<template>
  <section id="about" class="about-section">
    <div class="container mx-auto px-6 relative z-10">
      <header class="about-header reveal">
        <h2 class="title">About</h2>
      </header>

      <div class="about-layout reveal">
        <!-- LEFT TEXT -->
        <div class="about-text">
          <p class="lead">
            I’m a Computer Science student specializing in machine learning, backend development, and automation systems. I enjoy building practical AI solutions, full-stack tools, and data-driven applications. My work spans ML modeling, FastAPI-based automation, exploratory data analysis, and backend engineering. I’ve also participated in national hackathons and ML competitions, consistently working on projects that merge software engineering with intelligent systems.
          </p>

          <ul class="info-list">
            <li><strong>Languages:</strong> Python, SQL, C, Java, JavaScript</li>
            <li><strong>Skills:</strong> ML, DL, Data Analysis, Automation, FastAPI, Docker, Git, Linux, Generative AI</li>
            <li><strong>Interests:</strong> ML, DL, Generative AI, Backend Systems, Algorithms, Agentic AI</li>
            <li><strong>Currently:</strong> Working on automation tools, ML projects, and strengthening backend + AI engineering foundations</li>
          </ul>
        </div>

        <!-- RIGHT IMAGE -->
        <aside class="about-photo">
          <div class="photo-frame">
            <img src="/src/assets/placeholder-photo.png" alt="Riteesh TM" />
          </div>
        </aside>
      </div>

      <!-- Optional neon divider (matches projects + education) -->
      <div class="section-divider"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: "About"
}
</script>

<style scoped>
/* ---------------------------------------------------
   SECTION BASE (matches Education — open layout)
--------------------------------------------------- */
.about-section {
  padding: 3.4rem 0 2.6rem;
  position: relative;
  background: linear-gradient(180deg,
    rgba(255,255,255,0.00) 0%,
    rgba(255,255,255,0.01) 100%
  );
}

/* ---------------------------------------------------
   HEADER — clean, neon gradient text
--------------------------------------------------- */
.title {
  font-size: 1.9rem;
  font-weight: 800;
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 1rem;
}

.about-header {
  margin-bottom: 1.25rem;
}

/* ---------------------------------------------------
   TWO COLUMN LAYOUT (no card)
--------------------------------------------------- */
.about-layout {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  align-items: center;
}

@media (min-width: 860px) {
  .about-layout {
    grid-template-columns: 1.2fr 0.9fr;
  }
}

/* ---------------------------------------------------
   LEFT TEXT
--------------------------------------------------- */
.lead {
  color: rgba(230,240,255,0.92);
  font-size: 1.05rem;
  line-height: 1.7;
  max-width: 64ch;
}

.info-list {
  margin-top: 1rem;
  padding-left: 1.1rem;
  list-style: disc;
  color: rgba(180,195,210,0.60);
  line-height: 1.85;
}
.info-list strong {
  color: rgba(220,235,255,0.9);
}

/* ---------------------------------------------------
   PHOTO ON RIGHT (ENLARGED, RESPONSIVE, NON-BREAKING)
--------------------------------------------------- */
.about-photo {
  display: flex;
  justify-content: center;
}

/* Increased size for larger visual weight while preserving layout */
.photo-frame {
  width: 360px;               /* larger size */
  height: 360px;
  border-radius: 18px;       /* slightly rounded */
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.03);
  background: rgba(255,255,255,0.01);
  box-shadow:
    0 36px 80px rgba(0,0,0,0.72),
    0 0 48px rgba(6,182,212,0.06);
  transition: transform .32s cubic-bezier(.2,.9,.3,1), box-shadow .32s;
}

/* Make sure the image fills the frame nicely */
.photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Subtle hover lift with enhanced glow */
.photo-frame:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow:
    0 48px 110px rgba(0,0,0,0.78),
    0 0 80px rgba(6,182,212,0.10);
}

/* ---------------------------------------------------
   CYBER DIVIDER (thin neon fade)
--------------------------------------------------- */
.section-divider {
  height: 1px;
  width: 100%;
  margin-top: 3rem;
  background: radial-gradient(circle, rgba(6,182,212,0.20), transparent 70%);
  opacity: 0.25;
}

/* ---------------------------------------------------
   Reveal Animation
--------------------------------------------------- */
.reveal {
  opacity: 0;
  transform: translateY(18px);
  transition: all .7s cubic-bezier(.2,.9,.3,1);
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* ---------------------------------------------------
   SMALL / MEDIUM SCREENS — avoid overflow & preserve balance
--------------------------------------------------- */
@media (max-width: 1100px) {
  /* keep the image reasonably sized on medium screens */
  .photo-frame {
    width: 360px;
    height: 360px;
  }

  /* text max width reduced so lines are comfortable next to the bigger image */
  .lead { max-width: 56ch; }
}

@media (max-width: 900px) {
  .about-layout { grid-template-columns: 1fr; }
  .photo-frame {
    width: 300px;
    height: 300px;
    border-radius: 14px;
  }
  .lead { max-width: 100%; }
}

@media (max-width: 520px) {
  .photo-frame { width: 180px; height: 180px; }
  .lead { font-size: 1rem; line-height: 1.6; }
}
</style>
