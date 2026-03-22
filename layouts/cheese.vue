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
      <div style="flex:1;display:flex;flex-direction:row;align-items:stretch;">
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
