<script setup lang="ts">
import Modal from './components/Modal.vue'
import HelloWorld from './components/HelloWorld.vue'
import Navigation from './components/Navigation.vue'

import {ref} from "vue";

const showModal = ref(true);

function toggleModal() {
  showModal.value = !showModal.value;
}

</script>

<template>

  <Navigation />
  <HelloWorld msg="App" />
  <button @click="toggleModal()">Show Modal</button>
  <Modal v-if="showModal" title="Tutorial" text="Tutorial Video will be added eventually. Enjoy this instead." @close-modal="toggleModal()"/>
</template>

<style scoped>

</style>