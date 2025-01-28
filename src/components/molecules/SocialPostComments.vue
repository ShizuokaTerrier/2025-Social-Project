<template>
  <div class="comments">
    <p>Comments:</p>
    <div v-for="(comment, index) in comments" :key="index">
      <strong>This is comment number {{ index }}</strong>
      <p>{{ comment }}</p>
    </div>
  </div>
</template>
<script setup lang="ts">
defineProps({
  comments: Array,
})
</script>
<style lang="scss">
.comments {
  border: 5px solid black;
  margin: 3px auto;
  padding: 5px;
  border-radius: 10px;
  min-width: 60%;
  max-width: fit-content;
}
</style>
