<template>
  <div class="pb-12">
    <h3 class="text-center text-2xl text-yellow font-title">
      Le trailer de {{ film.title_quebec }} (en québécois),:
    </h3>
    <iframe
      class="trailer-video"
      :src="'https://www.youtube.com/embed/' + film.trailer"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; gyroscope;"
      allowfullscreen
    ></iframe>
  </div>
</template>
<script>
export default {
  props: ["film"],
};
</script>

<style scoped>
.trailer-video {
  aspect-ratio: 16 / 9;
  width: 100%;
}
</style>
