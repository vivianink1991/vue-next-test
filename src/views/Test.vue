<template>
  <div class="about">
    <h1>This is a test page</h1>
    <div>{{counter}}</div>
    <div>DoubleCounter: {{doubleCounter}}</div>
    <button @click="add">add</button>
  </div>
</template>
<script>
import { ref, computed, watch } from 'vue'

export default {
  name: 'Test',
  setup () {
    const counter = ref(0)
    const add = () => {
      counter.value++
    }
    const doubleCounter = computed(() => counter.value * 2)

    watch(() => counter.value, val => {
      console.log(`counter is ${val}`)
    })
    return {
      counter,
      add,
      doubleCounter
    }

  }
}
</script>
