<template>
  <div>
    <Header />
    <main class="pt-20">
      <Hero />
      <About />
      <Projects />
      <Contact />
    </main>
    <footer class="py-8 text-center text-sm text-gray-500">© {{ year }} — Riteesh TM</footer>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: { Header, Hero, About, Projects, Contact },
  data() { return { year: new Date().getFullYear() } }
}
</script>
