<script setup>
import { nextTick, reactive, shallowReactive, isReactive } from "vue";

const state = reactive({
  count: 0,
  nested: { count: 0 },
  arr: ["foo", "bar"],
});
const { count } = state;

function increame() {
  state.count++;
  console.log(state.count);
  nextTick(() => {
    state.nested.count += 2;
    state.arr.push(state.nested.count);
  });
  obj.nested.count.a++;
}
const obj = shallowReactive({
  foo: 1,
  nested: {
    count: {
      a: 1,
    },
  },
});
</script>
<template>
  <div>state: {{ state.count }}</div>
  <div>coutn: {{ count }}</div>
  <div>nested-state: {{ state.nested.count }}</div>
  <div>arr: {{ state.arr }}</div>
  <div>obj: {{ obj.nested.count.a }}</div>
  <button @click="increame">composition +</button>
</template>
