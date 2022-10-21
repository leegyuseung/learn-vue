<template><div></div></template>

<script>
import { reactive, ref } from "vue";

export default {
  setup() {
    // ref를 객체에서 사용
    const count = ref(0);
    const state = reactive({
      count: count,
    });
    count.value++;
    count.value++;
    console.log(count.value);
    console.log("state.count", state.count);

    // ref를 array에서 사용
    const message = ref("hello");
    const arr = reactive([message]);
    console.log("arr[0]", arr[0].value);
    return {};
  },
};
</script>

<style></style>
