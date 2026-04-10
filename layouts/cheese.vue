<script setup>
defineProps({
  gutter: { type: String, default: 'Defense in Depth' }
})
</script>

<template>
  <div class="slidev-layout slide-base cheese-slide">
    <div class="body">
      <div class="content-gutter">
        <div class="gutter-label">{{ gutter }}</div>
      </div>
      <div class="cheese-main">
        <div class="cheese-diagram">
          <slot name="diagram" />
        </div>
        <div class="cheese-info">
          <slot name="info" />
        </div>
      </div>
    </div>
  </div>
</template>
