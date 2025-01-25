<script setup lang="ts">
import { reactive } from 'vue'
import SocialPost from './molecules/SocialPost.vue'

const posts = reactive([
  {
    username: 'username 1',
    userId: 'usernameId1',
    avatarSrc: 'https://i.pravatar.cc/40',
    post: 'This is my post',
  },
  {
    username: 'username 2',
    userId: 'usernameId2',
    avatarSrc: 'https://i.pravatar.cc/40',
    post: 'This is my post, too',
  },
])
</script>

<template>
  <div>
    <SocialPost
      :username="posts[0].username"
      :userId="posts[0].userId"
      :avatarSrc="posts[0].avatarSrc"
      :post="posts[0].post"
    ></SocialPost>
    <SocialPost
      :username="posts[1].username"
      :userId="posts[1].userId"
      :avatarSrc="posts[1].avatarSrc"
      :post="posts[1].post"
    ></SocialPost>
  </div>
</template>

<style></style>
