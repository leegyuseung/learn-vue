<template></template>

<script>
import { reactive, readonly } from "vue";

export default {
  setup() {
    const original = reactive({
      count: 0,
    });
    // readonly의 count는 변경할 수 없다.
    const copy = readonly(original);
    original.count++;
    // copy.count++; error발생한다.
    console.log(original.count);
    console.log(copy.count);
    return {};
  },
};
</script>

<style></style>
