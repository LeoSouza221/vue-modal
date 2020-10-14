<template>
  <div class="vue-modal">
    <div data-toggle="modal" :data-target="`#id${idModal}`">
      <slot name="activator"></slot>
    </div>
    <div class="modal fade show"
      :id="`id${idModal}`"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Modal title</h5>
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
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalComponent',

  props: {
    value: {
      default: false,
      type: Boolean,
    },
    width: {
      type: Number,
    },
  },

  data: () => ({
    idModal: new Date().getTime(),
  }),

  computed: {
    modalWidth() {
      return this.width ? `width: ${this.width}px` : '';
    },
  },

  watch: {
    value() {
      if (this.value) {
        this.openModal();
        return;
      }
      this.closeModal();
    },
  },
};
</script>
