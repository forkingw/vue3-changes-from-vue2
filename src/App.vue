<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { onMounted, ref } from "vue";
import Composition from "./components/Composition.vue";
import Option from "./components/Option.vue";
// import HelloWorld from "./components/HelloWorld.vue";
// import MyModal from "./components/MyModal.vue";
// import EmitTest from "./components/EmitTest.vue";
// const helloRef = ref(null);

const one = ref(null);
const two = ref(null);
onMounted(() => {
  // console.log("helloRef", helloRef.value.increment());
  console.log("one", one);
  console.log("two", two);
  console.log(
    "one.value.click === two.value.click",
    one.value.click === two.value.click
  );
});
</script>

<template>
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld ref="helloRef">
    <span>this is slot</span>
  </HelloWorld> -->
  <!-- <component :is="HelloWorld" /> -->
  <!-- <div class="outer">
    <h3>Vue Teleport Example</h3>
    <div>
      <MyModal></MyModal>
    </div>
  </div> -->
  <!-- <EmitTest></EmitTest> -->
  <Composition />
  <hr />
  <Option ref="one" />
  <Option ref="two" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
