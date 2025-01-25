<script setup lang="ts">
import TheWelcome from './components/TheWelcome.vue'
import StaticFooter from './components/molecules/StaticFooter.vue'
import TheHeader from './components/organisms/TheHeader.vue'
</script>

<template>
  <div>
    <TheHeader />
    <TheWelcome />
    <StaticFooter name="Matt Keighley" />
  </div>
</template>

<style></style>
