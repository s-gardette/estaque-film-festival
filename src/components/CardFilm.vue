<template>
  <div
    data-aos="fade-up"
    data-aos-offset="0"
    data-aos-duration="1000"
    data-aos-easing="ease-in-out"
    data-aos-mirror="true"
    data-aos-once="false"
    data-aos-anchor-placement="top-bottom"
  >
    <div class="z-10 movie_card film peer hover:shadow-2xl">
      <div class="info_section pb-8 md:pb-16">
        <div class="movie_header">
          <img class="locandina" :src="'posters/' + film.poster" />
          <h1 class="font-title uppercase">{{ film.title }}</h1>
          <h4 class="font-cursive">{{ film.date }}, {{ film.director }}</h4>
          <p class="font-bold text-xl font-title">
            <span class="text-yellow">{{ film.schedule }}</span>
          </p>

          <p class="text-white font-body">
            <span class="minutes text-yellow font-bold mr-4">{{
              film.duration
            }}</span>
            <span v-for="type in film.types" :key="type" class="text-xs pr-4">{{
              type
            }}</span>
          </p>
        </div>
        <ModalFilm :film="film" />

        <div class="movie_desc">
          <p class="text font-body">
            {{ film.synopsys }}
          </p>
        </div>
        <div class="movie_quote">
          <p
            class="text-yellow shadow absolute right-0 pr-5 bottom-5 text-xl font-cursive max-w-xs"
          >
            {{ film.quote }}
          </p>
        </div>
      </div>
      <div
        class="blur_back film_back"
        :style="{
          background: 'url(images/' + film.poster + ')',
          backgroundSize: 'cover',
          backgroundRepeat: 'no-repeat',
          backgroundPosition: 'center',
        }"
      ></div>
    </div>
    <div
      class="z-5 background hidden peer-hover:block fixed w-screen h-screen top-0 left-0 opacity-50 bg-color-blue"
      :style="{
        background: 'url(images/' + film.poster + ')',
        backgroundSize: 'cover',
        backgroundRepeat: 'no-repeat',
        backgroundPosition: 'center',
      }"
    ></div>
  </div>
</template>

<script setup>
import ModalFilm from "./ModalFilm.vue";
</script>

<script>
export default {
  props: ["film"],
};
</script>

<style scoped lang="scss">
.movie_card {
  position: relative;
  display: block;
  height: 450px;
  overflow: hidden;
  border-radius: 2px;
  transition: all 0.4s;
  &:hover {
    transform: scale(1.08);
    transition: all 0.4s;
  }
  .info_section {
    position: relative;
    width: 100%;
    height: 100%;
    background-blend-mode: multiply;
    z-index: 2;
    border-radius: 2px;
    .movie_header {
      position: relative;
      padding: 25px;
      height: 40%;
      h1 {
        color: #fff;
        font-weight: 400;
      }
      h4 {
        color: #9ac7fa;
        font-weight: 400;
      }
      .minutes {
        display: inline-block;
        margin-top: 10px;
        padding: 5px;
        border-radius: 2px;
        border: 1px solid rgba(255, 255, 255, 0.13);
      }
      .type {
        display: inline-block;
        color: #cee4fd;
        margin-left: 10px;
      }
      .locandina {
        position: relative;
        float: left;
        margin-right: 20px;
        height: 120px;
        box-shadow: 0 0 20px -10px rgba(0, 0, 0, 0.5);
      }
    }
    .movie_desc {
      padding: 25px;
      height: 50%;
      .text {
        color: #cfd6e1;
      }
    }
    .movie_quote {
      padding-left: 15px;
      padding-bottom: 20px;
    }
  }
  .blur_back {
    position: absolute;
    top: 0;
    z-index: 1;
    height: 100%;
    width: 100%;
    right: 0;
    background-size: cover;
    border-radius: 2px;
  }
}

@media screen and (min-width: 768px) {
  .movie_header {
    width: 60%;
  }

  .movie_desc {
    width: 50%;
  }

  .info_section {
    background: linear-gradient(to right, #1a3852 50%, transparent 100%);
  }

  .blur_back {
    width: 80%;
    background-position: 50% 50% !important;
  }
}

@media screen and (max-width: 768px) {
  .movie_card {
    width: 99%;
    margin: 10px auto;
    min-height: 350px;
    height: auto;
  }

  .blur_back {
    width: 100%;
    background-position: 50% 50% !important;
  }

  .movie_header {
    width: 100%;
    margin-top: 85px;
  }

  .movie_desc {
    width: 100%;
  }

  .info_section {
    background: linear-gradient(to top, #1a3852 50%, transparent 100%);
    display: inline-grid;
  }
}
</style>
