<template>
  <section id="about" class="about-section">
    <div class="container mx-auto px-6">
      <div class="about-grid">
        <!-- LEFT: Text -->
        <div class="about-text">
          <h2 class="text-2xl font-bold">About</h2>

          <p class="mt-4 lead">
            I’m a CS student focusing on AI/ML, networking and embedded systems.
            I enjoy hackathons (SIH), DeepRacer experiments and building automation
            agents in FastAPI.
          </p>

          <ul class="about-list mt-6">
            <li>Languages: Python, C, Java</li>
            <li>Interests: Algorithms, ML, Embedded</li>
            <li>Currently: Preparing for exams & building a vehicle parking app</li>
          </ul>
        </div>

        <!-- RIGHT: Profile image -->
        <div class="about-image-wrap">
          <div class="profile-frame accent-outline">
            <!-- keep the filename you used earlier -->
            <img src="/src/assets/placeholder-photo.png" alt="Riteesh" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "About",
};
</script>

<style scoped>
/* Section spacing tightened so About sits closer under the hero */
.about-section {
  padding-top: 2.25rem;   /* reduced from big values */
  padding-bottom: 3.5rem;
  position: relative;
  z-index: 10;
  max-width: 100%;
  overflow-x: hidden;
}

/* Grid: on desktop, text takes 2/3 and image 1/3 */
.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
  align-items: center;
}
@media (min-width: 768px) {
  .about-grid {
    grid-template-columns: 2fr 1fr;
    gap: 2.5rem;
  }
}

/* Left column */
.about-text .lead {
  color: rgba(230,240,255,0.88);
  font-size: 1.05rem;
  line-height: 1.6;
  max-width: 60ch;
}

/* List style tuned for dark background */
.about-list {
  margin-left: 1rem;
  color: rgba(170,188,200,0.55);
  list-style: disc;
  line-height: 1.9;
  margin-top: 0.6rem;
}
.about-list li {
  margin-bottom: 0.4rem;
}

/* Right column: profile frame smaller and more subtle */
.about-image-wrap {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Reuse card/profile styles but smaller for balance */
.profile-frame {
  width: 192px;
  height: 192px;
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.04);
  box-shadow: 0 18px 56px rgba(0,0,0,0.75);
  background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.006));
  transition: transform .28s ease, box-shadow .28s ease;
}
.profile-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Accent outline (matching cyber theme) */
.accent-outline {
  box-shadow: 0 0 28px rgba(6,182,212,0.05), inset 0 0 40px rgba(139,92,246,0.02);
  border: 1px solid rgba(6,182,212,0.06);
}

/* subtle hover lift on profile */
.profile-frame:hover {
  transform: translateY(-6px);
  box-shadow: 0 28px 80px rgba(0,0,0,0.75), 0 0 24px rgba(6,182,212,0.03);
}

/* Small screens: reduce image size a bit */
@media (max-width: 420px) {
  .profile-frame { width: 140px; height: 140px; }
  .about-text .lead { font-size: 0.98rem; }
}
</style>
