<template>
  <section>
    <h2
      class="z-10 text-center my-10 md:my-16 text-xl md:text-3xl text-blue font-title"
    >
      Le prochain Film (C'est l'ouverture Youpi !!!)
    </h2>
    <CardFilm
      class="px-12 pb-12"
      :film="films[0]"
      :key="films[0].titre"
    ></CardFilm>
  </section>
</template>

<script setup>
import CardFilm from "./CardFilm.vue";
</script>

<script>
import json from "../assets/films.json";
export default {
  data() {
    return {
      films: json,
    };
  },
};
</script>
