<template>
  <div v-memo="[views, likes]">
    <p>{{ subscribers }}</p>
    <p>{{ views }}</p>
    <p>{{ likes }}</p>
  </div>
  <button @click="subscribers++">subs++</button>
  <button @click="views++">views++</button>
  <button @click="likes++">likes++</button>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const subscribers = ref(4000);
    const views = ref(400);
    const likes = ref(20);
    return { subscribers, views, likes };
  },
};
</script>

<style></style>
