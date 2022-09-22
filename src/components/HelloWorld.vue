<script setup>
import { onMounted, ref, useAttrs, useSlots } from "vue";

defineProps({
  msg: String,
});

// const c = await test();
// console.log("c", c);
const initialData = ref(null);
// test().then((res) => {
//   initialData.value = res;
// });
const theme = ref("red");
setTimeout(() => {
  theme.value = "green";
}, 3000);
async function init() {
  initialData.value = await test();
}
init();

const count = ref(0);
function increment() {
  count.value++;
}

onMounted(() => {
  console.log("The initial count is ${count.value}");
});

console.log("hello script setup");

defineExpose({
  increment,
});
</script>
<script>
function test() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(1);
    }, 3000);
  });
  console.log("aaa");
}
export default {
  name: "HelloWorldName",
};
</script>
<template>
  <button @click="increment">Count is {{ count }}-{{ initialData }}</button>
  <!-- <span>{{ msg }}</span>
  <span>{{ a }}</span> -->
  <span v-for="i in 10">{{ i }}</span>
  <div v-if="count">Yes</div>
  <div v-else>No</div>
</template>
<style>
span {
  color: v-bind(theme);
}
</style>
