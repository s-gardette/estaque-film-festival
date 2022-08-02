<template>
  <div>
    <div class="movie_card film peer">
      <div class="info_section">
        <div class="movie_header">
          <img class="locandina" :src="'posters/' + film.poster" />
          <h1 class="font-title uppercase">{{ film.title }}</h1>
          <h4 class="font-cursive">2017, {{ film.director }}</h4>

          <p class="text-white font-body">
            <span class="minutes text-yellow font-bold">{{
              film.duration
            }}</span>
            {{ film.types }}
          </p>
        </div>
        <div class="movie_desc">
          <p class="text font-body">
            {{ film.synopsys }}
          </p>
        </div>
        <div class="movie_social">
          <p
            class="text-yellow shadow absolute right-0 pr-10 text-xl font-cursive"
          >
            {{ film.quote }}
          </p>
          <button>En savoir Plus</button>
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
      class="background hidden peer-hover:block absolute w-screen h-screen top-0 left-0"
      :style="{
        background: 'url(images/' + film.poster + ')',
        backgroundSize: 'cover',
        backgroundRepeat: 'no-repeat',
        backgroundPosition: 'center',
      }"
    ></div>
  </div>
</template>

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
  border-radius: 10px;
  transition: all 0.4s;
  &:hover {
    transform: scale(1.02);
    transition: all 0.4s;
  }
  .info_section {
    position: relative;
    width: 100%;
    height: 100%;
    background-blend-mode: multiply;
    z-index: 2;
    border-radius: 10px;
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
        border-radius: 5px;
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
    .movie_social {
      height: 10%;
      padding-left: 15px;
      padding-bottom: 20px;
      ul {
        list-style: none;
        padding: 0;
        li {
          display: inline-block;
          color: rgba(255, 255, 255, 0.4);
          transition: color 0.3s;
          transition-delay: 0.15s;
          margin: 0 10px;
          &:hover {
            transition: color 0.3s;
            color: rgba(255, 255, 255, 0.8);
          }
          i {
            font-size: 19px;
            cursor: pointer;
          }
        }
      }
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
    border-radius: 11px;
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
    width: 95%;
    margin: 70px auto;
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
    background: linear-gradient(to top, rgb(20, 20, 19) 50%, transparent 100%);
    display: inline-grid;
  }
}
</style>
