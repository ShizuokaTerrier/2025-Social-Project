<template>
  <button :class="[size, theme]">
    {{ value }}
  </button>
</template>
<script lang="ts">
defineProps({
  value: {
    type: [String, Number],
    required: true,
  },
  width: {
    type: String,
    default: '100px',
  },
  theme: {
    type: String,
    default: 'light',
    validator: (value) => ['light', 'dark'].includes(value as string),
  },
})
</script>
<style scoped>
.normal {
  padding: 8px 16px;
  font-size: 16px;
}
.large {
  padding: 16px 32px;
  font-size: 24px;
}
.light {
  background-color: #1da1f2;
  color: white;
}
.dark {
  background-color: black;
  color: #1da1f2;
}
</style>
