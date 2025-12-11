<template>
  <section id="contact" class="contact-section">
    <div class="container mx-auto px-6">
      <header class="mb-6">
        <h2 class="title">Contact</h2>
        <p class="subtitle">Reach out — I respond to collaboration, internships, and hackathon ideas.</p>
      </header>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 items-start">
        <!-- Email card -->
        <div class="info-card">
          <div class="card-label">EMAIL</div>
          <div class="card-row">
            <div class="card-main">
              <a :href="`mailto:${email}`" class="card-link" @click.prevent="openMail">
                <div class="card-text">{{ email }}</div>
              </a>
            </div>

            <button class="copy-btn" @click="copyEmail" :aria-label="'Copy ' + email">
              <svg viewBox="0 0 24 24" width="18" height="18" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M16 4H8a2 2 0 0 0-2 2v12" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
                <rect x="9" y="2" width="11" height="14" rx="2" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </button>
          </div>
          <div v-if="copied" class="copied">Copied!</div>
        </div>

        <!-- LinkedIn card -->
        <div class="info-card">
          <div class="card-label">LINKEDIN</div>
          <div class="card-row">
            <div class="card-main">
              <a :href="linkedin" target="_blank" rel="noopener" class="card-link">
                <div class="card-text">{{ linkedinText }}</div>
              </a>
            </div>
            <div class="card-action-placeholder"></div>
          </div>
        </div>
      </div>

      <!-- GitHub CTA (full width on mobile) -->
      <div class="mt-8">
        <a :href="github" target="_blank" rel="noopener" class="github-cta" role="button">
          <div class="cta-left">
            <!-- github icon -->
            <svg class="gh-icon" viewBox="0 0 24 24" width="28" height="28" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <path fill="currentColor" d="M12 0.5a12 12 0 0 0-3.8 23.4c0.6 0.11 0.8-0.26 0.8-0.58 0-0.29 0-1.04-0.02-2.05-3.3 0.72-4-1.6-4-1.6-0.55-1.4-1.35-1.78-1.35-1.78-1.1-0.76 0.08-0.75 0.08-0.75 1.22 0.08 1.86 1.26 1.86 1.26 1.08 1.85 2.85 1.32 3.54 1.01 0.11-0.78 0.42-1.32 0.77-1.62-2.64-0.3-5.42-1.32-5.42-5.9 0-1.3 0.47-2.36 1.24-3.19-0.12-0.3-0.54-1.52 0.12-3.17 0 0 1.02-0.33 3.35 1.22a11.5 11.5 0 0 1 6.1 0c2.33-1.55 3.34-1.22 3.34-1.22 0.66 1.65 0.24 2.87 0.12 3.17 0.77 0.83 1.24 1.89 1.24 3.19 0 4.6-2.79 5.6-5.44 5.9 0.43 0.37 0.82 1.1 0.82 2.22 0 1.6-0.02 2.88-0.02 3.27 0 0.32 0.21 0.7 0.82 0.58A12 12 0 0 0 12 0.5z"/>
            </svg>

            <div class="cta-text">
              <div class="cta-title">View my GitHub</div>
              <div class="cta-sub">Repos, experiments and projects — code-first.</div>
            </div>
          </div>

          <div class="cta-right">
            <div class="cta-pill">Open on GitHub ↗</div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      email: "riteesh.meganathan@gmail.com",
      linkedin: "https://www.linkedin.com/in/riteeshtm07",
      linkedinText: "linkedin.com/in/riteeshtm07",
      github: "https://github.com/RiteeshTM",
      copied: false
    }
  },
  methods: {
    copyEmail() {
      navigator.clipboard?.writeText(this.email).then(() => {
        this.copied = true
        setTimeout(() => (this.copied = false), 1400)
      }).catch(() => {
        // fallback
        this.copied = true
        setTimeout(() => (this.copied = false), 1400)
      })
    },
    openMail() {
      // open mail client in new tab (works better UX on some setups)
      window.location.href = `mailto:${this.email}`
    }
  }
}
</script>

<style scoped>
.contact-section { padding: 3.25rem 0 4rem; }

/* header */
.title { font-size: 1.8rem; font-weight: 800; margin-bottom: 0.25rem;
  background: linear-gradient(90deg,#06B6D4,#8B5CF6);
  -webkit-background-clip:text; -webkit-text-fill-color:transparent;
}
.subtitle { color: rgba(170,188,200,0.6); margin-bottom: 1.25rem; }

/* info card */
.info-card {
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.006));
  border: 1px solid rgba(255,255,255,0.03);
  border-radius: 8px;
  padding: 14px 16px;
  display:flex;
  flex-direction: column;
  gap: 8px;
  box-shadow: 0 18px 56px rgba(0,0,0,0.7);
}

.card-label { font-size: 11px; color: rgba(170,188,200,0.48); letter-spacing: .06em; }
.card-row { display:flex; align-items:center; gap:12px; }

.card-main { flex: 1; }
.card-link { display:block; text-decoration:none; color: inherit; }
.card-text { font-weight:700; font-size:16px; color: rgba(230,240,255,0.95); }

/* copy button */
.copy-btn {
  border: 1px solid rgba(255,255,255,0.04);
  background: transparent;
  padding: 8px;
  border-radius: 8px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;
  color: rgba(200,220,235,0.9);
  transition: transform .12s ease, box-shadow .18s;
}
.copy-btn:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(6,182,212,0.06); }

/* small copied label */
.copied {
  color: var(--accent, #06B6D4);
  font-size: 13px;
  margin-top: 4px;
}

/* GitHub CTA */
.github-cta {
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap: 12px;
  padding: 18px;
  border-radius: 12px;
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.008));
  border: 1px solid rgba(255,255,255,0.03);
  text-decoration:none;
  color: inherit;
  box-shadow: 0 28px 72px rgba(0,0,0,0.7);
  transition: transform .28s cubic-bezier(.2,.9,.3,1), box-shadow .28s, background .18s;
  isolation:isolate;
}
.github-cta:hover { transform: translateY(-10px); box-shadow: 0 42px 110px rgba(0,0,0,0.85); border-color: rgba(6,182,212,0.08); }
.github-cta:active { transform: translateY(-6px); }

/* left side */
.cta-left { display:flex; gap:14px; align-items:center; }
.gh-icon { color: #BFEFF6; filter: drop-shadow(0 6px 18px rgba(6,182,212,0.06)); }
.cta-text { display:flex; flex-direction:column; }
.cta-title { font-weight:800; font-size:18px; color: rgba(230,240,255,0.95); }
.cta-sub { font-size:13px; color: rgba(170,188,200,0.62); margin-top:2px; }

/* right side pill */
.cta-right { display:flex; align-items:center; }
.cta-pill {
  padding:8px 12px;
  border-radius:999px;
  background: linear-gradient(90deg, rgba(6,182,212,0.06), rgba(139,92,246,0.04));
  color: #E8FBFF;
  font-weight:600;
  border: 1px solid rgba(6,182,212,0.06);
  transition: transform .12s ease;
}
.github-cta:hover .cta-pill { transform: translateY(-3px); }

/* responsive */
@media (max-width: 760px) {
  .grid { grid-template-columns: 1fr; }
  .github-cta { flex-direction: column; align-items: flex-start; gap: 10px; }
  .cta-right { width:100%; display:flex; justify-content:flex-end; }
}

/* match accent variable fallback */
:root { --accent: #06B6D4; }
</style>
