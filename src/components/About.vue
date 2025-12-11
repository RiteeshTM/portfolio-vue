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
            I’m a CS student focusing on AI/ML, networking and embedded systems.
            I enjoy hackathons (SIH), DeepRacer experiments, and building automation
            agents in FastAPI.
          </p>

          <ul class="info-list">
            <li><strong>Languages:</strong> Python, C, Java</li>
            <li><strong>Interests:</strong> Algorithms, ML, Embedded</li>
            <li><strong>Currently:</strong> Preparing for exams & building a vehicle parking app</li>
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
   PHOTO ON RIGHT
--------------------------------------------------- */
.about-photo {
  display: flex;
  justify-content: center;
}

.photo-frame {
  width: 240px;
  height: 240px;
  border-radius: 14px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.03);
  background: rgba(255,255,255,0.01);
  box-shadow: 0 18px 56px rgba(0,0,0,0.7);
  transition: transform .25s ease;
}

.photo-frame img {
  width:100%;
  height:100%;
  object-fit:cover;
}

.photo-frame:hover {
  transform: translateY(-6px);
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
   Small Screens
--------------------------------------------------- */
@media (max-width: 520px) {
  .photo-frame { width: 180px; height: 180px; }
}
</style>
