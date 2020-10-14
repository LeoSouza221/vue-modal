<template>
  <VueModal
    v-model="dialog"
  >
    <template v-slot:activator>
      <h1>a</h1>
    </template>
  </VueModal>
</template>

<script>
import VueModal from './VueModal.vue';

export default {
  name: 'Teste',

  data: () => ({
    dialog: false,
  }),

  components: {
    VueModal,
  },
};
</script>
