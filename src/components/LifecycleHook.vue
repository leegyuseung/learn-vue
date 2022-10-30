<template>
  <div class="container py-4">
    <input type="text" ref="inputRef" value="hello world" />
    <hr />
    <button @click="visible = !visible">toggle</button>
    <LifecycleChild v-if="visible"></LifecycleChild>
    <p id="message">
      {{ message }}
    </p>
  </div>
</template>

<script>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from "vue";
import LifecycleChild from "./LifecycleChild.vue";

export default {
  setup() {
    // console.log("setup");
    const inputRef = ref(null);
    const message = ref("");
    const visible = ref(false);
    // onBeforeMount(() => {
    //   console.log("onBeforeMount");
    // });
    // onMounted(() => {
    //   console.log("onMounted", inputRef.value.value);
    // });

    // onBeforeUpdate(() => {
    //   console.log("onBeforeUpdate", message.value);
    //   console.log(document.querySelector("#message").textContent);
    // });
    // onUpdated(() => {
    //   console.log("onUpdated", message.value);
    //   console.log(document.querySelector("#message").textContent);
    // });
    return { inputRef, message, visible };
  },
  components: { LifecycleChild },
  // beforeCreate() {
  //   console.log("beforeCreate");
  // },
  // created() {
  //   console.log("created");
  // },
};
</script>

<style></style>
