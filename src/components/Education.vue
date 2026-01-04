<!-- Source: Resume_Riteesh.pdf -->
<template>
  <section id="education" class="education-section">
    <div class="container mx-auto px-6 relative z-10">
      <header class="edu-header">
        <h2 class="title">Education</h2>
        <p class="subtitle">Academic background & certifications.</p>
      </header>

      <div class="edu-grid">

        <!-- B.Tech -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">B.Tech — Computer Science & Engineering</div>
              <div class="inst">Amrita Vishwa Vidyapeetham, Coimbatore</div>
            </div>
            <div class="edu-right">
              <div class="period">2023 — 2027</div>
            </div>
          </div>

          <div class="edu-desc">
            <strong>CGPA:</strong> 9.00 / 10<br />
            Relevant coursework: Algorithms, Data Structures, Operating Systems, Computer Networks, Database Systems.
          </div>
        </article>

        <!-- IIT Madras BS Degree -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">BS — Data Science & Applications</div>
              <div class="inst">IIT Madras (BS Programme)</div>
            </div>
            <div class="edu-right">
              <div class="period">2023 — Present</div>
            </div>
          </div>

          <div class="edu-desc">
            <strong>GPA:</strong> 8.20 / 10<br />
            Coursework: Machine Learning, Data Science, Statistics, Programming, Business Analytics.
          </div>
        </article>

        <!-- Higher Secondary (HSC) -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">Higher Secondary (HSC)</div>
              <div class="inst">Srimathi Sundaravalli Memorial School, Chennai</div>
            </div>
            <div class="edu-right">
              <div class="period">2020 — 2021</div>
            </div>
          </div>

          <div class="edu-desc">
            <strong>Score:</strong> 463 / 500<br />
          </div>
        </article>

        <!-- Senior Secondary (SSC / Class 10) -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">Senior Secondary (SSC)</div>
              <div class="inst">Srimathi Sundaravalli Memorial School, Chennai</div>
            </div>
            <div class="edu-right">
              <div class="period">2022 — 2023</div>
            </div>
          </div>

          <div class="edu-desc">
            <strong>Score:</strong> 480 / 500<br />
          </div>
        </article>

      </div>

      <!-- Certifications row -->
      <header class="edu-header" style="margin-top:1.75rem;">
        <h3 class="title" style="font-size:1.25rem;">Certifications</h3>
        <p class="subtitle" style="margin-top:.125rem;">Selected professional programs & certificates.</p>
      </header>

      <div class="edu-grid" style="margin-top:0.6rem;">

        <!-- Azure Fundamentals -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">
                <a href="https://learn.microsoft.com/en-us/users/riteeshmeganathan-6816/credentials/71ed5effd7d09397?ref=https%3A%2F%2Fwww.linkedin.com%2F" target="_blank" class="cert-link">
                  Azure Fundamentals
                </a>
              </div>
              <div class="inst">Microsoft</div>
            </div>
            <div class="edu-right">
              <div class="period">Jul 2023</div>
            </div>
          </div>
          <div class="edu-desc">Foundational cloud concepts and Azure services.</div>
        </article>

        <!-- Programming & Data Science -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">
                <a href="https://drive.google.com/file/d/1FOsaRfCcp4dk4JRprNlCygfNr1pd3ZAy/view" target="_blank" class="cert-link">
                  Programming & Data Science
                </a>
              </div>
              <div class="inst">IIT Madras — BS Programme</div>
            </div>
            <div class="edu-right">
              <div class="period">Sep 2024</div>
            </div>
          </div>
          <div class="edu-desc">Core programming and data science fundamentals.</div>
        </article>

        <!-- Advanced ML & DS -->
        <article class="edu-card reveal" tabindex="0">
          <div class="edu-row">
            <div class="edu-left">
              <div class="degree">
                <a href="https://drive.google.com/file/d/1sCXMMtGNCFzJZXkoGHsAxhjoDsHmgwK6/view" target="_blank" class="cert-link">
                  Advanced Certificate in Machine Learning & Data Science
                </a>
              </div>
              <div class="inst">IIT Madras — BS Programme</div>
            </div>
            <div class="edu-right">
              <div class="period">Aug 2025</div>
            </div>
          </div>
          <div class="edu-desc">ML topics, model evaluation, and Business Analytics.</div>
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

.edu-row { display:flex; justify-content:space-between; align-items:center; gap: 0.6rem; }
.degree { font-weight:700; color: rgba(235,245,255,0.94); }
.inst { color: rgba(170,188,200,0.6); font-size: .95rem; margin-top: .2rem; }
.period {
  font-size: .95rem;
  color: rgba(6,182,212,0.92);
  padding: 6px 10px;
  border-radius:999px;
  background: rgba(6,182,212,0.06);
  border: 1px solid rgba(6,182,212,0.06);
}

.edu-desc { margin-top: 0.8rem; color: rgba(170,188,200,0.5); line-height: 1.6; }

.cert-link {
  color: rgba(235,245,255,0.94);
  text-decoration: none;
  transition: color .25s ease;
}
.cert-link:hover {
  color: #06B6D4;
  text-decoration: underline;
}

.reveal { opacity:0; transform: translateY(18px) scale(.995); transition: all .7s cubic-bezier(.2,.9,.3,1); }
.reveal.visible { opacity:1; transform: translateY(0) scale(1); }
</style>
