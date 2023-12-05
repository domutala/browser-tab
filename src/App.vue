<script setup lang="ts">
import BrowserTab from './components/BrowserTab.vue'
</script>

<template>
  <div>
    <BrowserTab :tabs="{ test: { title: 'Test' }, 'page-2': { title: 'page-2' } }">
      <template #test>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusantium sed molestiae ratione
        assumenda. Optio, odio ea iure maiores distinctio possimus deleniti? Quidem natus eligendi
        laudantium voluptates itaque earum aliquid delectus!
      </template>

      <template #page-2>
        page 2 Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusantium sed molestiae
        ratione assumenda. Optio, odio ea iure maiores distinctio possimus deleniti? Quidem natus
        eligendi laudantium voluptates itaque earum aliquid delectus!
      </template>
    </BrowserTab>
  </div>
</template>
