<script setup>
defineProps({
  leftLabel: { type: String, default: '' },
  leftTitle: { type: String, default: '' },
  leftItems: { type: Array, default: () => [] },
  rightLabel: { type: String, default: '' },
  rightTitle: { type: String, default: '' },
  rightItems: { type: Array, default: () => [] }
})
</script>

<template>
  <div class="compare-grid">
    <div class="compare-col">
      <div v-if="leftLabel" class="compare-col-label">{{ leftLabel }}</div>
      <div v-if="leftTitle" class="compare-col-title">{{ leftTitle }}</div>
      <div class="compare-items">
        <div v-for="(item, i) in leftItems" :key="i" class="compare-item">{{ item }}</div>
      </div>
    </div>
    <div class="compare-col">
      <div v-if="rightLabel" class="compare-col-label">{{ rightLabel }}</div>
      <div v-if="rightTitle" class="compare-col-title">{{ rightTitle }}</div>
      <div class="compare-items">
        <div v-for="(item, i) in rightItems" :key="i" class="compare-item">{{ item }}</div>
      </div>
    </div>
  </div>
</template>
