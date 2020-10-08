<template>
  <div class="modal-editar">
    <div class="modal fade" :id="`modalComponent${idModal}`" data-backdrop="static" tabindex="-1" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered" :style="modalWidth">
        <div class="modal-content">
          <slot name="content-modal"></slot>
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
          required: true,
          default: false,
          type: Boolean,
      },
      width: {
          required: false,
          type: Number,
      }
  },

  data: () => ({
    idModal: new Date().getTime(),
  }),

  computed: {
    modalWidth() {
      return this.width ? `width: ${this.width}px` : '';
    }
  },

  methods: {
    openModal() {
      $(`#modalComponent${this.idModal}`).modal('show');
    },

    closeModal() {
      $(`#modalComponent${this.idModal}`).modal('hide');
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
}    
</script>
