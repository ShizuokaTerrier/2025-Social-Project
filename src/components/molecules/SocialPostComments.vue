<template>
  <div class="SocialPostcomments">
    <p>Comments:</p>
    <div v-for="(comment, index) in comments" :key="index" class="comment">
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
<style scoped lang="scss">
SocialPostComments {
  padding-left: 24px;
  p {
    font-weight: bold;
  }
  .comment {
    display: flex;
    justify-content: space-between;
    background-color: var(--color-input-mute);
    border-radius: 10px;
    margin-bottom: 8px;
    padding: 8px 16px;
    color: var(--color-background-soft);
    width: 75%;
  }
  svg {
    fill: var(--color-background-mute);
  }
}
</style>
