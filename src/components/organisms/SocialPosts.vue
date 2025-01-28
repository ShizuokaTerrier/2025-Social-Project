<template>
  <div>
    <SocialPost
      v-for="post in posts"
      :username="post.username"
      :userId="post.userId"
      :avatarSrc="post.avatar"
      :post="post.post"
      :comments="post.comments"
      :likes="post.likes"
      :retweets="post.retweets"
      :tags="post.tags"
      :key="post.userId"
      @delete="onDelete"
    />
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import SocialPost from '../molecules/SocialPost.vue'

const posts = reactive([
  {
    username: 'Username one',
    userId: 'usernameId1',
    avatar: 'https://i.pravatar.cc/40',
    post: 'This is my post',
    comments: ['great post', 'amazing post'],
    likes: 2,
    retweets: 1,
    tags: ['tag 1'],
  },
  {
    username: 'Username two',
    userId: 'usernameId2',
    avatar: 'https://i.pravatar.cc/40',
    post: 'This is my second post',
    comments: [],
    likes: 2,
    retweets: 1,
    tags: ['tag 1', 'tag 2'],
  },
])

const onDelete = () => {
  posts.splice(0, 1)
}
</script>

<style></style>
