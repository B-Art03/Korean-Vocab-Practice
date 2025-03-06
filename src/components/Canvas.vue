<script setup lang="ts">

</script>

<template>
<canvas id="canvas">
  <p></p>
  Your browser does not support the HTML5 canvas tag.
  I can add all the components I need here. I need a Setup or Mode Selector Component and then the actual "game" component (either 3D for now or 2D later) will be rendered with its own component. So I guess I don't need the Canvas here after all.
</canvas>
</template>

<style scoped>
* {
  background: #F0EFF7;
}
canvas {
  border: 1px solid black;
  display: block;
  margin: 0 auto;
  width: 100%;
  height: 100%;
  max-height: 1200px;
}
h1
{
  text-align: center;
  color: black;
}
</style>