<template>
  <section>
    <h2
      class="z-10 text-center my-10 md:mb-8 text-xl md:text-3xl text-blue font-title"
    >
      Le prochain Film (C'est l'ouverture Youpi !!!)
    </h2>
    <h2
      class="bg-blue z-10 text-center my-10 text-xl md:text-3xl text-yellow font-title"
    >
      Visionnage : {{ film.schedule }} <br />
      Lieu : {{ film.location }}
    </h2>
    <h3 class="text-center">
      <a
        class="underline font-body text-blue hover:text-green"
        :href="'https://www.google.com/maps/search/?api=1&query=43.36219328461216,5.3149513937961865'"
        >Comment se rendre au lieu de visionnage ?</a
      >
    </h3>
    <CardFilm class="px-4 pb-12" :film="film" :key="film.titre"></CardFilm>
  </section>
</template>

<script setup>
import CardFilm from "./CardFilm.vue";
</script>

<script>
import json from "../assets/films.json";
export default {
  data() {
    const films = json;
    const film = films[2];
    return {
      film,
    };
  },
};
</script>
