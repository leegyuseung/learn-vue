<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ reverseMessage }}</p>
  </div>
</template>

<script>
import { ref, watch } from "vue";

export default {
  setup() {
    const message = ref("Hello Vue3");
    const reverseMessage = ref("");

    const reverseFunction = (newValue) => {
      console.log("즉시실행!");
      reverseMessage.value = newValue.split("").reverse().join("");
    };

    watch(message, reverseFunction);
    reverseFunction(message.value);
    // watch(
    //   message,
    //   (newValue) => {
    //     reverseMessage.value = newValue.split("").reverse().join("");
    //   },
    //   // 즉시 실행을 위해 3번째 인자로 {} 안에 immediate :true
    //   { immediate: true }
    // );
    return { message, reverseMessage };
  },
};
</script>

<style></style>
