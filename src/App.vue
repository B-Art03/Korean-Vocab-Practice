<script setup lang="ts">
import Modal from './components/Modal.vue'
import Navigation from './components/Navigation.vue'

import {ref} from "vue";
import WordList from "./components/WordList.vue";
import Canvas from "./components/Canvas.vue";
import AnswerBar from "./components/AnswerBar.vue";

const showModal = ref(false);

function toggleModal() {
  showModal.value = !showModal.value;
}

</script>

<template>
  <Navigation title="Korean Vocabulary Practice" @open-tutorial="toggleModal()" />
  <div class="canvas">
    <Canvas/>
  </div>
  <AnswerBar/>
  <WordList/>
  <Modal v-if="showModal" title="Tutorial" text="Tutorial Video will be added eventually. Enjoy this instead." @close-modal="toggleModal()">
    <iframe src="https://www.youtube.com/embed/Sagg08DrO5U?si=6h6qqjMdITXxrs7E" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  </Modal>
</template>

<style scoped>

</style>