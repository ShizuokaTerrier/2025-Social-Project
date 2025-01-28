<template>
  <div class="SocialPost" :class="{ SocialPost__selected: selected }" @click="onSelectedClick">
    <div class="header">
      <img class="avatar" :src="avatarSrc" alt="avatar" />
      <div class="name">{{ username }}</div>
      <div class="userId">{{ userId }}</div>
      <IconDelete @click="onDeleteClick" />
    </div>
    <div class="post">{{ post }}</div>
    <div class="interactions">Interactions:{{ interactions }}</div>
    <button v-if="hasComments" @click="onShowComments">Show Comments</button>
  </div>
  <SocialPostComments v-if="showComments" :comments="comments" />
</template>
<script setup lang="ts">
import { onMounted, ref, computed } from 'vue'
import SocialPostComments from './SocialPostComments.vue'
import IconDelete from '../icons/IconDelete.vue'
const selected = ref(false)
const showComments = ref(false)
const props = defineProps({
  username: {
    type: String,
    default: 'Mystery User!',
  },
  userId: String,
  avatarSrc: String,
  post: String,
  comments: Array,
  likes: Number || undefined,
  retweets: Number || undefined,
})

const onSelectedClick = () => {
  selected.value = !selected.value
}

const onShowComments = () => {
  showComments.value = !showComments.value
}

const hasComments = computed(() => {
  return props.comments?.length ?? 0
})

const interactions = computed(() => {
  const totalInteractions =
    (props.comments?.length || 0) + (props.likes || 0) + (props.retweets || 0)
  return totalInteractions
})

onMounted(() => {
  console.log(props.username)
})
const emit = defineEmits(['delete'])
const onDeleteClick = () => {
  emit('delete')
}
</script>
<style lang="scss">
.SocialPost {
  margin-bottom: 16px;
  &__selected {
    border: white solid 1px;
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
    color: black;
  }
  .interactions {
    display: flex;
    font-weight: bold;
    margin-top: 8px;
    gap: 8px;
    svg {
      width: 24px;
      height: 24px;
      fill: var(--color-border);
    }
  }
}
</style>
