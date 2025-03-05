<script setup lang="ts">
  import { ref, defineProps} from 'vue'

  const props = defineProps({
    title: {
      type: String,
      default: 'Tutorial',
      required: true
    },
    text: {
      type: String,
      default: 'Tutorial',
      required: true
    }
  })

  const emit = defineEmits({
    'close-modal': null
  })

  function closeModal() {
    emit('close-modal');
  }

</script>

<template>
<div class="backdrop" @click.self="closeModal">
  <div class="modal">
    <button @click="closeModal">Close</button>
    <h1>{{ title }}</h1>
    <p>{{ text }}</p>
    <div class="content">

      <slot></slot>
    </div>
  </div>
</div>
</template>

<style scoped>
  .modal {
    width: 90%;
    height: 80%;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
    position: relative; /* Makes the modal the reference for absolute positioning */
    display: flex;
    flex-direction: column;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
  }
  .modal button {
    position: absolute;
    top: 10px;
    right: 10px;
    background-color: red;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 5px 10px;
  }
  .content {
    flex: 1;
    display: flex;
    margin-top: 10px;
    justify-content: center;
    align-items: center;
    overflow: hidden;
  }
  :deep(.modal iframe) {
    display: block;
    aspect-ratio: 16 / 9;
    height: auto;
    width: 100%;
    max-width: 1500px;
  }
  h1 {
    color: red;
    text-align: center;
    font-size: 40px;
  }
</style>