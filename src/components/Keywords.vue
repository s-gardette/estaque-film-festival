<template>
  <div class="mb-4">
    <h3 class="text-center text-2xl text-yellow font-title mb-4 px-8">
      Les thémes importants du film selon TheMovieDB (c'est rigolo):
    </h3>
    <p class="font-title text-center text-white text-xl">{{ film.keywords }}</p>
  </div>
</template>
<script>
export default {
  props: ["film"],
};
</script>
