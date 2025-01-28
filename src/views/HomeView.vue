<script setup lang="ts">
import TheHeader from '@/components/organisms/TheHeader.vue'
import SocialPosts from '@/components/organisms/SocialPosts.vue'
import StaticFooter from '@/components/molecules/StaticFooter.vue'
import SideBar from '@/components/organisms/SideBar.vue'
import CreatePost from '@/components/molecules/CreatePost.vue'
</script>

<template>
  <TheHeader />
  <SideBar />
  <main>
    <CreatePost />
    <SocialPosts />
  </main>
  <StaticFooter name="Matt Keighley" />
</template>

<style scoped>
@import '../assets/base.css';
aside {
  border-right: 1px solid var(--color-border);
  padding: 16px 32px;
}
main {
  padding: 16px 32px;
}
</style>
