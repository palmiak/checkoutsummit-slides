<script setup>
defineProps({
  gutter: { type: String, default: '' }
})
</script>

<template>
  <div class="slidev-layout slide-base content-slide">
    <div class="body">
      <div class="content-gutter">
        <div class="gutter-label">{{ gutter }}</div>
      </div>
      <div class="content-main">
        <slot />
      </div>
    </div>
  </div>
</template>
