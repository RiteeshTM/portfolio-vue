<template>
  <header
    class="fixed w-full z-30 backdrop-blur-md bg-black/20 border-b border-white/5"
  >
    <div
      class="container mx-auto px-6 py-4 flex items-center justify-between"
    >
      <!-- Left: Icon + Name -->
      <div class="flex items-center gap-3">
        
        <!-- 🔥 COOL GLOWING TECH ICON -->
        <div class="w-7 h-7 flex items-center justify-center">
          <svg
            class="w-full h-full"
            viewBox="0 0 100 100"
            xmlns="http://www.w3.org/2000/svg"
          >
            <!-- Outer glow -->
            <circle cx="50" cy="50" r="40" fill="none"
              stroke="#06B6D4" stroke-width="3"
              opacity="0.35"
              style="filter: drop-shadow(0 0 12px #06B6D4)"
            />

            <!-- Hex core -->
            <polygon
              points="50,20 73,35 73,65 50,80 27,65 27,35"
              fill="none"
              stroke="#06B6D4"
              stroke-width="3"
              style="filter: drop-shadow(0 0 10px #06B6D4)"
            />

            <!-- Inner glow dot -->
            <circle cx="50" cy="50" r="6" fill="#06B6D4"
              style="filter: drop-shadow(0 0 10px #06B6D4)"
            />
          </svg>
        </div>

        <div class="font-semibold text-white tracking-wide text-lg">
          Riteesh TM
        </div>
      </div>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex gap-6 text-sm text-white/70">
        <a href="#about" class="hover:text-white transition">About</a>
        <a href="#projects" class="hover:text-white transition">Projects</a>
        <a href="#contact" class="hover:text-white transition">Contact</a>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
/* no custom CSS needed — SVG carries its own glow */
</style>
