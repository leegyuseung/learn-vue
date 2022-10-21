<template>
  <div>
    <p>{{ message.value }}</p>
    <button @click="addMessage">add click</button>
  </div>
  <div>
    <p>{{ message2 }}</p>
    <button @click="addMessage2">add click</button>
  </div>
</template>

<script>
import { reactive, ref } from "vue";

export default {
  setup() {
    // reactive는 객체 타입에서만 반응한다. 대안: ref함수
    let message = reactive({
      value: "hello vue",
    });
    let message2 = ref("hello vue");

    const addMessage = () => {
      message.value = message.value + "!";
    };

    const addMessage2 = () => {
      message2.value = message2.value + "!";
    };

    return { message, addMessage, message2, addMessage2 };
  },
};
</script>

<style></style>
