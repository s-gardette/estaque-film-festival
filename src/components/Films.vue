<template>
  <section>
    <h2>Les films du festival</h2>
    <div class="flex flex-wrap gap-8">
      <CardFilm
        class="md:w-1/2"
        v-for="film in films"
        :film="film"
        :key="film.titre"
      ></CardFilm>
    </div>
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
