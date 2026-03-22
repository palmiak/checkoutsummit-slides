<script setup>
defineProps({
  label: { type: String, default: '' },
  number: { type: String, default: '' },
  sublabel: { type: String, default: '' },
  sub: { type: String, default: '' },
  numberColor: { type: String, default: 'default' },
  numberSize: { type: String, default: '' }
})
</script>

<template>
  <div>
    <div v-if="label" class="s-label">{{ label }}</div>
    <div
      class="stat-number"
      :class="{
        'danger': numberColor === 'danger',
        'green': numberColor === 'green'
      }"
      :style="numberSize ? { fontSize: numberSize } : {}"
    >{{ number }}</div>
    <div v-if="sublabel" class="stat-label">{{ sublabel }}</div>
    <div v-if="sub" class="stat-sub">{{ sub }}</div>
  </div>
</template>
