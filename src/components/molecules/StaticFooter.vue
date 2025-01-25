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
  min-height: 100%;
  min-width: 100%;
}
footer {
  display: flex;
  justify-content: center;
  padding: 5px;
  background-color: black;
  color: #fff;
}
</style>
