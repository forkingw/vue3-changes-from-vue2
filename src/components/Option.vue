<script>
import { debounce } from "lodash-es";
export default {
  data() {
    return {
      count: 1,
    };
  },
  mounted() {
    // this.increament();
  },
  methods: {
    increament() {
      // this.count++;
      console.log(this);
    },
    click: debounce(function () {
      this.count++;
      console.log("---", this.count);
    }, 1500),
  },
};
</script>

<template>
  {{ count }}
  <button @click="click">click</button>
</template>
