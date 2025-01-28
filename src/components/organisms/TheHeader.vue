<template>
  <header>
    <div v-html="logo"></div>

    <h1>Companion App</h1>
    <a href="#"> Welcome <span v-text="username"></span> </a>
  </header>
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
header {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  grid-column-start: 1;
  grid-column-end: 3;
  padding-bottom: 24px;
  border-bottom: solid 1px black;

  .span {
    display: flex;
  }
  a {
    font-size: 16px;
    line-height: 24px;
    margin-right: 8px;
    font-weight: bolder;
  }
}
</style>
