<script setup>
defineProps({
  variant: {
    type: String,
    default: 'default'
  },
  label: {
    type: String,
    default: ''
  },
  labelAccent: {
    type: String,
    default: 'default'
  }
})
</script>

<template>
  <div
    class="block"
    :class="{
      'red-border': variant === 'red',
      'amber-border': variant === 'amber',
      'green-border': variant === 'green'
    }"
  >
    <div
      v-if="label"
      class="block-label"
      :class="{
        'accent': labelAccent === 'red',
        'accent-amber': labelAccent === 'amber',
        'accent-green': labelAccent === 'green'
      }"
    >{{ label }}</div>
    <slot />
  </div>
</template>
