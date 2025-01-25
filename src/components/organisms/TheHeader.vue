<template>
  <div class="TheHeader">
    <header>
      <div v-html="logo"></div>

      <h1>Companion App</h1>
      <a href="#"> Welcome <span v-text="username"></span> </a>
    </header>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
const username = ref('Matt')
const logo = `<svg
height="50"
width="50"
viewbox="0 0 210 210">
<polygon
points="100,10 40,198 190,78 10,78 160,198"
style="fill:grey;"/>
</svg>`
</script>
<style lang="scss">
.theHeader {
  min-height: 100%;
  min-width: 100%;
  padding: 5px;
}
header {
  display: flex;
  justify-content: center;
  gap: 12px;
  padding: 5px;
  background-color: black;
  color: #fff;
}
</style>
