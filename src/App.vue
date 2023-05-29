<script setup>
import { ref } from  'vue'
import modalUserInfo from './components/userModalDialog.vue'

const isOpenDialog = ref(false);

function setStatusDialog(value) {
  isOpenDialog.value = value;
}
</script>

<template>
  <main>
    <h1>Vue Component</h1>
    <button @click="setStatusDialog(true)">Open Modal</button>

    <modal-user-info v-if="isOpenDialog" :key="isOpenDialog.value" :is-active-dialog="isOpenDialog" @close-dialog="setStatusDialog">
      <h3>My Modal Info</h3>
    </modal-user-info>
  </main>
</template>
