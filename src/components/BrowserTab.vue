<script setup lang="ts">
import { ref, type PropType } from 'vue'

const props = defineProps({
  tabs: {
    type: [Array, Object] as PropType<string[] | { [key: string]: { title: string } }>,
    default: () => []
  }
})
const currentTab = ref('')

function getTtile(key: string) {
  if (Array.isArray(props.tabs)) return key

  return props.tabs[key].title
}
</script>

<template>
  <div>
    <div class="tabs">
      <div name="window" v-for="(tab, t) in tabs" :key="t" @click="currentTab = t">
        {{ getTtile(t as string) }}
      </div>
    </div>
    <div class="windows">
      <div v-for="(tab, t) in tabs" :key="t" v-show="t === currentTab">
        <slot :name="t" :props="{ tab }"></slot>
      </div>
    </div>
  </div>
</template>
