<template>
  <div>
    <h3 class="text-center text-2xl text-yellow font-title">
      Les thémes importants du film selon TheMovieDB (c'est rigolo):
    </h3>
    <p class="font-title text-white tex-xl">{{ film.keywords }}</p>
  </div>
</template>
<script>
export default {
  props: ["film"],
};
</script>
