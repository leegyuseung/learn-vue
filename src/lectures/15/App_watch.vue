<template>
  <div></div>
</template>

<script>
import { ref, watch } from "vue";

export default {
  setup() {
    const message = ref("");
    watch(message, (newValue, oldValue) => {
      // 또다른 dom 조작
      // api
      // state 변경
      console.log("newValue:", newValue);
      console.log("oldValue:", oldValue);
    });
    return { message };
  },
};
</script>

<style></style>
