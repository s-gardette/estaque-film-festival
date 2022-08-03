<template>
  <div>
    <section id="content" class="min-h-screen min-w-screen bg-yellow text-blue">
      <Logo class="z-10 relative" id="logo" />
      <FilmNext />
      <Films />
    </section>
    <Footer />
    <Install />
  </div>
</template>

<script setup>
import Footer from "./components/Footer.vue";
import Logo from "./components/Logo.vue";
import Films from "./components/Films.vue";
import FilmNext from "./components/FilmNext.vue";
import Install from "./components/Install.vue";
</script>

<style></style>
