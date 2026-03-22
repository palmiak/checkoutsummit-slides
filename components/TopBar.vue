<script setup>
defineProps({
  color: {
    type: String,
    default: 'red'
  }
})
</script>

<template>
  <div class="top-bar" :class="color" />
</template>
