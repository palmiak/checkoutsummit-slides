<script setup>
defineProps({
  color: {
    type: String,
    default: 'red'
  }
})
</script>

<template>
  <ul class="blist" :class="color">
    <slot />
  </ul>
</template>
