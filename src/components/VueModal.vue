<template>
  <div class="vue-modal">
    <div
      data-toggle="modal"
      :data-target="`#id${idModal}`"
      class="pointer"
    >
      <slot name="activator"></slot>
    </div>
    <div class="modal fade"
      :id="`id${idModal}`"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <slot name="modal-content"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalComponent',

  props: {
    align: {
      type: String,
      default: 'center',
    },
    width: {
      type: Number,
    },
  },

  data: () => ({
    idModal: new Date().getTime(),
    aligns: {
      center: {
      },
      top: {
      },
    },
  }),

  computed: {
    modalWidth() {
      return this.width ? `width: ${this.width}px` : '';
    },
  },
};
</script>

<style scoped>
  .pointer {
    cursor: pointer;
  }
</style>
