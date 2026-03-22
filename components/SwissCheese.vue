<script setup>
defineProps({
  activeLayer: {
    type: Number,
    default: 1
  }
})
</script>

<template>
  <!-- Layer 1: Network active, slices 2 & 3 ghost -->
  <svg v-if="activeLayer === 1" viewBox="0 0 800 640" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;">
    <defs>
      <marker id="arr1" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto">
        <polygon points="0 0,8 3,0 6" fill="var(--red)"/>
      </marker>
    </defs>
    <!-- Slice 1: active rectangle -->
    <rect x="215" y="45" width="100" height="540" fill="rgba(255,255,255,0.09)" stroke="rgba(255,255,255,0.35)" stroke-width="1.5"/>
    <circle cx="265" cy="200" r="38" fill="var(--bg)"/>
    <circle cx="252" cy="310" r="12" fill="var(--bg)"/>
    <circle cx="268" cy="405" r="20" fill="var(--bg)"/>
    <circle cx="255" cy="495" r="14" fill="var(--bg)"/>
    <circle cx="280" cy="125" r="9"  fill="var(--bg)"/>
    <!-- Ghost slice 2 -->
    <rect x="385" y="45" width="100" height="540" fill="rgba(255,255,255,0.02)" stroke="rgba(255,255,255,0.08)" stroke-width="1" stroke-dasharray="4 3"/>
    <!-- Ghost slice 3 -->
    <rect x="555" y="45" width="100" height="540" fill="rgba(255,255,255,0.02)" stroke="rgba(255,255,255,0.08)" stroke-width="1" stroke-dasharray="4 3"/>
    <!-- Arrow: enters from left, tip at hole left edge -->
    <line x1="5" y1="200" x2="227" y2="200" stroke="var(--red)" stroke-width="2" stroke-dasharray="5 3" marker-end="url(#arr1)"/>
    <!-- Continues through hole and past -->
    <line x1="303" y1="200" x2="800" y2="200" stroke="var(--red)" stroke-width="2" stroke-dasharray="5 3" opacity="0.28"/>
  </svg>

  <!-- Layer 2: Application active — slice 1 dim, slice 2 active, slice 3 ghost -->
  <svg v-else-if="activeLayer === 2" viewBox="0 0 800 640" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;">
    <defs>
      <marker id="arr2" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto">
        <polygon points="0 0,8 3,0 6" fill="var(--red)"/>
      </marker>
    </defs>
    <!-- Slice 1: dim -->
    <rect x="215" y="45" width="100" height="540" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.15)" stroke-width="1"/>
    <circle cx="265" cy="200" r="38" fill="var(--bg)"/>
    <circle cx="252" cy="310" r="12" fill="var(--bg)"/>
    <circle cx="268" cy="405" r="20" fill="var(--bg)"/>
    <circle cx="255" cy="495" r="14" fill="var(--bg)"/>
    <circle cx="280" cy="125" r="9"  fill="var(--bg)"/>
    <!-- Slice 2: active -->
    <rect x="385" y="45" width="100" height="540" fill="rgba(255,255,255,0.09)" stroke="rgba(255,255,255,0.35)" stroke-width="1.5"/>
    <circle cx="435" cy="270" r="20" fill="var(--bg)"/>
    <circle cx="442" cy="380" r="16" fill="var(--bg)"/>
    <circle cx="422" cy="115" r="11" fill="var(--bg)"/>
    <circle cx="450" cy="475" r="10" fill="var(--bg)"/>
    <!-- Ghost slice 3 -->
    <rect x="555" y="45" width="100" height="540" fill="rgba(255,255,255,0.02)" stroke="rgba(255,255,255,0.08)" stroke-width="1" stroke-dasharray="4 3"/>
    <!-- Arrow: through hole in slice 1, hits solid wall of slice 2 -->
    <line x1="5" y1="200" x2="227" y2="200" stroke="var(--red)" stroke-width="2" stroke-dasharray="5 3"/>
    <line x1="303" y1="200" x2="385" y2="200" stroke="var(--red)" stroke-width="2" stroke-dasharray="5 3" marker-end="url(#arr2)"/>
    <!-- BLOCKED at slice 2 — X mark -->
    <line x1="385" y1="188" x2="403" y2="212" stroke="var(--green)" stroke-width="2"/>
    <line x1="403" y1="188" x2="385" y2="212" stroke="var(--green)" stroke-width="2"/>
    <!-- Second attack hits solid part of slice 1 -->
    <line x1="5" y1="310" x2="215" y2="310" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.5"/>
    <line x1="215" y1="299" x2="232" y2="321" stroke="var(--green)" stroke-width="1.5" opacity="0.5"/>
    <line x1="232" y1="299" x2="215" y2="321" stroke="var(--green)" stroke-width="1.5" opacity="0.5"/>
  </svg>

  <!-- Layer 3: All three — slices 1 & 2 dim, slice 3 active -->
  <svg v-else viewBox="0 0 800 640" xmlns="http://www.w3.org/2000/svg" style="width:100%;height:auto;">
    <!-- Slice 1: dim -->
    <rect x="215" y="45" width="100" height="540" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.15)" stroke-width="1"/>
    <circle cx="265" cy="200" r="38" fill="var(--bg)"/>
    <circle cx="252" cy="310" r="12" fill="var(--bg)"/>
    <circle cx="268" cy="405" r="20" fill="var(--bg)"/>
    <circle cx="255" cy="495" r="14" fill="var(--bg)"/>
    <circle cx="280" cy="125" r="9"  fill="var(--bg)"/>
    <!-- Slice 2: dim -->
    <rect x="385" y="45" width="100" height="540" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.15)" stroke-width="1"/>
    <circle cx="435" cy="270" r="20" fill="var(--bg)"/>
    <circle cx="442" cy="380" r="16" fill="var(--bg)"/>
    <circle cx="422" cy="115" r="11" fill="var(--bg)"/>
    <circle cx="450" cy="475" r="10" fill="var(--bg)"/>
    <!-- Slice 3: active -->
    <rect x="555" y="45" width="100" height="540" fill="rgba(255,255,255,0.09)" stroke="rgba(255,255,255,0.35)" stroke-width="1.5"/>
    <circle cx="605" cy="145" r="16" fill="var(--bg)"/>
    <circle cx="612" cy="275" r="14" fill="var(--bg)"/>
    <circle cx="598" cy="405" r="12" fill="var(--bg)"/>
    <circle cx="618" cy="500" r="9"  fill="var(--bg)"/>
    <!-- Arrow 1: through slice 1 hole, blocked by slice 2 -->
    <line x1="5" y1="200" x2="227" y2="200" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="303" y1="200" x2="385" y2="200" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="385" y1="189" x2="401" y2="211" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
    <line x1="401" y1="189" x2="385" y2="211" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
    <!-- Arrow 2: blocked by solid part of slice 1 -->
    <line x1="5" y1="310" x2="215" y2="310" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="215" y1="299" x2="232" y2="321" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
    <line x1="232" y1="299" x2="215" y2="321" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
    <!-- Arrow 3: through holes in slices 1 & 2, blocked by slice 3 -->
    <line x1="5" y1="405" x2="227" y2="405" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="303" y1="405" x2="385" y2="405" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="415" y1="405" x2="555" y2="405" stroke="var(--red)" stroke-width="1.5" stroke-dasharray="5 3" opacity="0.45"/>
    <line x1="555" y1="394" x2="572" y2="416" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
    <line x1="572" y1="394" x2="555" y2="416" stroke="var(--green)" stroke-width="1.5" opacity="0.45"/>
  </svg>
</template>
