<script>
import Modal from "./Modal.vue";

export default {
  components: {
    Modal,
  },
  data() {
    return {
      showModal: false,
    };
  },
};
</script>

<template>
  <button class="text-white" id="show-modal" @click="showModal = true">
    Show Modal
  </button>

  <Teleport to="body">
    <!-- use the modal component, pass in the prop -->
    <modal :show="showModal" @close="showModal = false">
      <template #header>
        <h3>custom header</h3>
      </template>
      <template #body>
        <h3>custom header</h3>
      </template>
      <template #footer>
        <h3>custom header</h3>
      </template>
    </modal>
  </Teleport>
</template>
