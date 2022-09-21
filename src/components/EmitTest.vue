<script>
export default {
  emits: {
    check: (val) => {
      console.log("val", val);
      if (val !== 1) {
        console.log("不等于1");
        return false;
      }
      return true;
    },
  },
  created() {
    console.log("EmitTest");
    this.$emit("check", 2);
  },
};
</script>
<template></template>
