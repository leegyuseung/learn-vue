<script setup>
import { isRef, onBeforeMount, onMounted, ref } from "vue";

const reactiveMessage = ref("hello Reactive Message");
const addReactiveMessage = () => {
  reactiveMessage.value = reactiveMessage.value + "!";
};
console.log(isRef(reactiveMessage)); //isRef : 반응형인지 확인한다.

let normalMessage = "Normal Message";
const addNormalMessage = () => {
  normalMessage = normalMessage + "!";
};
console.log(isRef(addNormalMessage));

// 라이프 사이클 훅
onMounted(() => {
  console.log("onMounted");
});
onBeforeMount(() => {
  console.log("onBeforeMount");
});
</script>

<template>
  <h1>반응형 메지지</h1>
  <p>{{ reactiveMessage }}</p>
  <button @click="addReactiveMessage">add message</button>

  <h1>일반 메지지</h1>
  <p>{{ normalMessage }}</p>
  <button @click="addNormalMessage">add message</button>
</template>

<style scoped></style>
