<script setup>
defineProps({
  filename: { type: String, default: '' },
  width: { type: String, default: 'min(540px,88%)' },
  height: { type: String, default: '340px' }
})
</script>

<template>
  <div class="img-ph" :style="{ width, height }">
    <span style="font-size:32px;opacity:.2;">&#9634;</span>
    {{ filename }}
  </div>
</template>
