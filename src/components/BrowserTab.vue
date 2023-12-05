<script setup lang="ts"></script>

<template>
  <div>
    <div class="tabs">
      <div name="window" v-for="i in 5" :key="i">{{ i }}</div>
    </div>
    <div class="windows">
      <div v-for="i in 5" :key="i">
        <slot :name="`${window}-${i}`" :props="{ tab: i }"></slot>
      </div>
    </div>
  </div>
</template>
