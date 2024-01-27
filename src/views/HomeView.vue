<script setup>
import { useCounterStore } from '../stores/counter'
import { storeToRefs } from 'pinia'
import { watch } from 'vue'

const { count } = storeToRefs(useCounterStore())

watch(count, (val) => {
  console.log('store中的count变化了', val)
})
</script>

<template>
  <main>
    {{ count }}
  </main>
  <button @click="count++">+</button>
</template>
