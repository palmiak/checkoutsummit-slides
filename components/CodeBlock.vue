<script setup>
defineProps({
  title: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <div class="code-wrap">
    <div v-if="title" class="code-bar">{{ title }}</div>
    <div class="code-body">
      <slot />
    </div>
  </div>
</template>
