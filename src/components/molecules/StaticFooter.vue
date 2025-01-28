<template>
  <div class="StaticFooter">
    <footer>
      <p>© {{ props.name }} {{ currentYear }}</p>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  name: String,
})
const currentYear = ref(new Date().getFullYear())
</script>

<style scoped lang="scss">
.StaticFooter {
  background-color: black;
  color: white;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  grid-column-start: 1;
  grid-column-end: 3;
}
</style>
