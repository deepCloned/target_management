<script setup lang="ts">
import { ref } from 'vue';
const dateList = ref([
  { startDate: '2022-11-14', endData: '2022-12-14' }
])

</script>

<template>
  <main>
    <ul>
      <li v-for="item of dateList" :key="item.startDate">
        startDate: {{item.startDate}}
        endData: {{item.endData}}
      </li>
    </ul>
  </main>
</template>
