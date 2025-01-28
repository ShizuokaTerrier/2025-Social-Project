<script setup lang="ts">
import { reactive } from 'vue'
import SocialPost from './molecules/SocialPost.vue'

const posts = reactive([
  {
    username: 'Username one',
    userId: 'usernameId1',
    avatar: 'https://i.pravatar.cc/40',
    post: 'This is my post',
    comments: ['great post', 'amazing post'],
    tags: ['tag 1'],
  },
  {
    username: 'Username two',
    userId: 'usernameId2',
    avatar: 'https://i.pravatar.cc/40',
    post: 'This is my second post',
    comments: [],
    tags: ['tag 1', 'tag 2'],
  },
])
</script>

<template>
  <div>
    <SocialPost
      v-for="(post, index) in posts"
      :username="post.username"
      :userId="post.userId"
      :avatarSrc="post.avatar"
      :post="post.post"
      :comments="post.comments"
      :tags="post.tags"
      :key="index"
    />
  </div>
</template>

<style></style>
