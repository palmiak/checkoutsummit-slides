<script setup>
defineProps({
  num: { type: String, default: '01' }
})
</script>

<template>
  <div class="chapter-bg-num">{{ num }}</div>
</template>
