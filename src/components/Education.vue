<template>
  <section id="education" class="education-section">
    <div class="container mx-auto px-6 relative z-10">
      <header class="edu-header">
        <h2 class="title">Education</h2>
        <p class="subtitle">Academic background & certifications.</p>
      </header>

      <div class="edu-grid">
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">B.Tech — Computer Science</div>
              <div class="inst">Amrita Vishwa Vidyapeetham</div>
            </div>
            <div class="edu-right">
              <div class="period">2021 — Present</div>
            </div>
          </div>
          <div class="edu-desc">Relevant coursework: Algorithms, Operating Systems, Networks, Data Structures. GPA / notable achievements can go here.</div>
        </article>

        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">Higher Secondary</div>
              <div class="inst">XYZ Higher Secondary School</div>
            </div>
            <div class="edu-right">
              <div class="period">2019 — 2021</div>
            </div>
          </div>
          <div class="edu-desc">Focus on Mathematics and Physics. Awards / certifications can be listed here.</div>
        </article>
      </div>
    </div>
  </section>
</template>

<script>
export default { name: "Education" }
</script>

<style scoped>
.education-section {
  padding: 3rem 0 3.5rem;
  background: linear-gradient(180deg, rgba(255,255,255,0.00), rgba(255,255,255,0.004));
  border-top: 1px solid rgba(255,255,255,0.02);
}

.edu-header { margin-bottom: 1.25rem; }
.edu-header .title {
  font-size: 1.6rem;
  font-weight: 800;
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.edu-header .subtitle { color: rgba(170,188,200,0.45); margin-top: .25rem; }

/* grid */
.edu-grid { display: grid; gap: 1rem; grid-template-columns: 1fr; }
@media (min-width: 760px) { .edu-grid { grid-template-columns: 1fr 1fr; } }

.edu-card {
  padding: 1.25rem;
  border-radius: 12px;
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.007));
  border: 1px solid rgba(255,255,255,0.03);
  box-shadow: 0 20px 48px rgba(0,0,0,0.6);
  transition: transform .28s ease, box-shadow .28s ease;
  position: relative;
}
.edu-card:hover, .edu-card:focus {
  transform: translateY(-8px);
  box-shadow: 0 28px 72px rgba(0,0,0,0.7);
  border-color: rgba(6,182,212,0.06);
}

/* layout inside card */
.edu-row { display:flex; justify-content:space-between; align-items:center; gap: 0.6rem; }
.degree { font-weight:700; color: rgba(235,245,255,0.94); }
.inst { color: rgba(170,188,200,0.6); font-size: .95rem; margin-top: .2rem; }
.period { font-size: .95rem; color: rgba(6,182,212,0.92); padding: 6px 10px; border-radius:999px; background: rgba(6,182,212,0.06); border: 1px solid rgba(6,182,212,0.06); }

/* description */
.edu-desc { margin-top: 0.8rem; color: rgba(170,188,200,0.5); line-height: 1.6; }

/* reveal animation */
.reveal { opacity:0; transform: translateY(18px) scale(.995); transition: all .7s cubic-bezier(.2,.9,.3,1); }
.reveal.visible { opacity:1; transform: translateY(0) scale(1); }
</style>
