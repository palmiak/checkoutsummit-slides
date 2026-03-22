<script setup>
defineProps({
  color: { type: String, default: 'purple' }
})
</script>

<template>
  <div class="slidev-layout slide-base chapter-slide" :class="`chapter-${color}`">
    <slot />
  </div>
</template>
