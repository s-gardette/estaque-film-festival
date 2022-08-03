<template>
  <div class="w-1/2 flex justify-center">
    <button
      class="text-yellow text-3xl font-cursive bg-green px-4 py-2 self-center rounded hover:shadow"
      id="show-modal"
      @click="showModal = true"
    >
      En savoir plus
    </button>
  </div>
  <Teleport to="body">
    <!-- use the modal component, pass in the prop -->
    <modal :show="showModal" @close="showModal = false">
      <template #body>
        <div class="pb-12">
          <h3 class="text-center text-2xl text-yellow font-title">
            Les commentaires des spécialistes sur {{ film.title }} :
          </h3>
          <div class="grid grid-cols-1 md::grid-cols-2 lg:grid-cols-3">
            <div
              class="block p-6 rounded shadow-lg bg-white m-4 bg-opacity-40 col-span-1"
              v-for="(comm, user) in film.comments"
              :key="user"
            >
              <div class="md:flex md:flex-row">
                <div
                  class="w-36 flex justify-center items-center mb-6 lg:mb-0 mx-auto md:mx-0"
                >
                  <img
                    :src="'users/' + user + '.png'"
                    class="rounded-full shadow-md object-cover"
                  />
                </div>
                <div class="md:ml-6">
                  <p class="text-white font-light mb-6 text-xl">
                    {{ comm }}
                  </p>
                  <p
                    class="font-semibold text-xl mb-2 font-cursive text-yellow text-right pr-20"
                  >
                    {{ user }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <Trailer :film="film" />
        <Keywords :film="film" />
      </template>
      <template #modal-bg>
        <div
          class="z-5 background absolute w-full h-full top-0 left-0 opacity-5 bg-color-blue-200"
          :style="{
            background: 'url(images/' + film.poster + ')',
            backgroundSize: 'cover',
            backgroundRepeat: 'no-repeat',
            backgroundPosition: 'center',
          }"
        ></div>
      </template>
    </modal>
  </Teleport>
</template>

<script setup>
import Modal from "./Modal.vue";
import Trailer from "./Trailer.vue";
import Keywords from "./Keywords.vue";
</script>

<script>
export default {
  components: {
    Modal,
    Trailer,
    Keywords,
  },
  data() {
    return {
      showModal: false,
    };
  },
  props: ["film"],
};
</script>
