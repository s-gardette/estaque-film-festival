<template>
  <div>
    <section id="content" class="min-h-screen min-w-screen bg-yellow text-blue">
      <Logo class="z-10 relative" id="logo" />
      <Films />
    </section>
    <Footer />
  </div>
</template>

<script setup>
import Footer from "./components/Footer.vue";
import Logo from "./components/Logo.vue";
import Films from "./components/Films.vue";
</script>

<style></style>
