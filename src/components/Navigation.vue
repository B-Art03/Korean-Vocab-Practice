<script setup lang="ts">
import { ref, defineProps, defineEmits} from 'vue'

defineProps<{ title: string }>()

const emit = defineEmits({
  'open-tutorial': null
})

function openTutorial() {
  emit('open-tutorial');
}

</script>

<template>
  <nav>
    <a href="https://vuejs.org/" target="_blank">
      <img src="../assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <h1>{{ title }}</h1>
    <button @click="openTutorial()">Tutorial</button>
  </nav>
</template>

<style scoped>
nav {
  background: #953D60;
  display: flex;
  justify-content: center;
  gap: 1em;
  padding: 5px 20px 20px;
  margin-bottom: 10px;
}
.logo {
  position: absolute;
  left: 3em;
  top: 2em;
  height: 3em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
a {
  color: white;
}
button {
  background: #DDBFE4;
  width: auto;
  height: 4em;
  position: absolute;
  right: 3em;
  top: 3em;
  color: black;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  cursor: pointer;
}
</style>