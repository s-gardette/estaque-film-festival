<template>
  <section>
    <h2>Les films du festival</h2>
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 px-12 pb-20">
      <CardFilm
        class="col-span-1"
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
