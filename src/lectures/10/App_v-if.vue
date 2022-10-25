<template>
  <div>
    <h2 v-if="visible">Hello vue3</h2>
    <h2 v-else>false 입니다</h2>
    <button @click="visible = !visible">toggle</button>
    <hr />

    <h2 v-if="type === A">A</h2>
    <h2 v-else-if="type === B">B</h2>
    <h2 v-else-if="type === C">C</h2>
    <h2 v-else>not ABC</h2>

    <button @click="type = 'A'">A</button>
    <button @click="type = 'B'">B</button>
    <button @click="type = 'C'">C</button>
    <button @click="type = 'D'">D</button>

    <template v-if="visible">
      <div>
        <h1>title</h1>
        <p>paragraph</p>
        <p>paragraph2</p>
      </div>
    </template>

    <hr />

    <h1 v-show="ok">Title</h1>
    <button @click="ok = !ok">show toggle</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const visible = ref(false);
    const type = ref("A");
    const ok = ref(true);
    return { ok, visible, type };
  },
};
</script>

<style></style>
