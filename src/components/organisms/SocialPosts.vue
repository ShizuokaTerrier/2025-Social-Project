<template>
  <div>
    <SocialPost
      v-for="(post, index) in posts"
      :username="post.username"
      :userId="post.userId"
      :avatarSrc="post.avatar"
      :post="post.post"
      :comments="post.comments"
      :likes="post.likes"
      :retweets="post.retweets"
      :tags="post.tags"
      :key="post.userId"
      @delete="onDelete(index)"
    />
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import SocialPost from '../molecules/SocialPost.vue'

interface Post {
  username: string
  userId: string
  avatar: string
  post: string
  comments: string[]
  likes: number
  retweets: number
  tags: string[]
}

type PostsResponse = Post[]

const posts = ref<PostsResponse>([])

onMounted(async () => {
  const response = await fetch('http://127.0.0.1:8000/posts?limit=3')
  const data: PostsResponse = await response.json()
  posts.value = data
})

const onDelete = (postIndex: number) => {
  posts.value.splice(postIndex, 1)
}
</script>

<style></style>
