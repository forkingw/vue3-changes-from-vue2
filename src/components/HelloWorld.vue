<script setup>
import { onMounted, ref, useAttrs, useSlots } from 'vue';

defineProps({
  msg: String
})
const slots = useSlots()
const attrs = useAttrs()
console.log('slots', slots);
console.log('attrs', attrs);

const count = ref(0)
function increment() {
  count.value ++
}

onMounted(() => {
  console.log('The initial count is ${count.value}');
})

console.log('hello script setup')

defineExpose({
  increment
})
</script>

<template>
  <button @click="increment">Count is {{ count }}</button>
</template>

