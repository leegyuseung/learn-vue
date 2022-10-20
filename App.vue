<template>
  <p>{{ counter }}</p>
  <p>{{ message }}</p>
  <button @click="increment">+button</button>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const counter = ref(0);
    const message = ref("hello vue3");
    const increment = () => {
      counter.value++;
    };

    return { counter, message, increment };
  },
};
</script>

<style></style>
