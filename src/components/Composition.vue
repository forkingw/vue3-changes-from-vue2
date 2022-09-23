<script setup>
import { computed, ref } from 'vue';

const count = ref(1)
// const plusOne = computed({
//   get: () => count.value + 1,
//   set: (val) => {
//     count.value = val - 1
//   }
// })
// plusOne.value = 1
// console.log('count.value', count.value)
// console.log(plusOne);
// plusOne.value++ is readonly
// function increase() {
//   plusOne.value += 1
// }
// const plusOne = computed(() => count.value + 1, {
//   onTrack(e) {
//     console.log('onTrack', e);
//     debugger
//   },
//   onTrigger(e) {
//     console.log('onTrigger', e);
//     debugger
//   }
// })
// function increase() {
//   count.value ++
// }
const plusOne = computed(() => 1)
console.log('plusOne', plusOne);
const plusTwo = computed(() => count.value ++)
console.log('plusTwo', plusTwo);
</script>

<template>
  <div>count: {{ count }}</div>
  <div>plusOne: {{ plusOne }}</div>
  <button @click="increase">+</button>
</template>