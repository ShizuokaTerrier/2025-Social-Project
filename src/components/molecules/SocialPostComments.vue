<template>
  <div>
    <p>Comments:</p>
    <div v-for="(comment, index) in comments">
      <strong>This is comment number {{ index }}</strong>
      <p>{{ comment }}</p>
    </div>
  </div>
</template>
<script setup lang="ts">
const props = defineProps({
  comments: Array,
})
</script>
