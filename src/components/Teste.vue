<template>
  <VueModal
    align="center"
  >
    <template v-slot:activator>
      <h1>a</h1>
    </template>
    <template v-slot:modal-content>
      <div class="modal-header">
        <h5 class="modal-title" id="staticBackdropLabel">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Understood</button>
      </div>
    </template>
  </VueModal>
</template>

<script>
import VueModal from './VueModal.vue';

export default {
  name: 'Teste',

  components: {
    VueModal,
  },
};
</script>
