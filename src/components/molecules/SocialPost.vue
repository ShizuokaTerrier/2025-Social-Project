<template>
  <div class="SocialPost" :class="{ SocialPost__selected: selected }" @click="selected = !selected">
    <div class="header">
      <img class="avatar" :src="avatarSrc" alt="avatar" />
      <div class="name">{{ username }}</div>
      <div class="userId">{{ userId }}</div>
    </div>
    <div class="post">{{ post }}</div>
    <button v-if="comments?.length ?? 0" @click="showComments = !showComments">
      Show Comments
    </button>
  </div>
  <SocialPostComments v-if="showComments" :comments="comments" />
</template>
<script setup lang="ts">
import { onMounted, ref } from 'vue'
import SocialPostComments from './SocialPostComments.vue'
const selected = ref(false)
const showComments = ref(false)
const props = defineProps({
  username: String,
  userId: String,
  avatarSrc: String,
  post: String,
  comments: Array,
})
onMounted(() => {
  console.log(props.username)
})
</script>
<style lang="scss">
.SocialPost {
  &__selected {
    border: 5px solid blue;
  }
  .header {
    display: flex;
    align-items: center;
    margin-bottom: 8px;
  }
  .avatar {
    border-radius: 50%;
    margin-right: 12px;
  }
  .name {
    font-weight: bold;
    margin-right: 8px;
    color: white;
  }
  border: 5px solid black;
  margin: 3px;
  padding: 5px;
  border-radius: 10px;
}
</style>
