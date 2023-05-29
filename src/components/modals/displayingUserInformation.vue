<script setup>
import { defineProps, defineEmits, toRefs } from 'vue';
const props = defineProps({
  isActiveDialog: Function,
});

const { isActiveDialog } = toRefs(props);

const emits = defineEmits({
  closeDialog: false,
});

const setUpdateInfoModalDialog = () => {
  emits('closeDialog', false);
};
</script>

<template>
  <div class="modal">
    <div class="modal-inner">
      <slot />
      <button class="modal-close" @click="setUpdateInfoModalDialog">Close</button>
    </div>
  </div>
</template>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  z-index: 99;

  background: rgba(0, 0, 0, 0.39);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-inner {
  background: #fff;
  padding: 30px 80px 30px 80px;
}
</style>
