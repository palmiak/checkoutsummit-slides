<script setup>
defineProps({
  source: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <div class="quote-wrap">
    <div class="quote-text"><slot /></div>
    <div v-if="source" class="quote-source">{{ source }}</div>
  </div>
</template>
