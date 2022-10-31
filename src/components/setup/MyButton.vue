<template>
  <div class="p-3 bg-danger">
    <!-- v-bind="$attrs" -->
    <button class="btn btn-primary" type="button" @click="sayHello">
      My Button {{ message }}
    </button>
    <!-- {{$attrs}} -->
  </div>
</template>

<script>
export default {
  // 속성상속 못하게한다.
  // inheritAttrs: false,
  emits: ["click"],
  setup(props, { emit }) {
    // console.log("context.attrs", context.attrs);
    // console.log("class", context.attrs.class);
    // console.log("id", context.attrs.id);
    // console.log("onClick", context.attrs.onClick);
    // context.attrs.onClick()
    const sayHello = () => {
      emit("click");
    };
    return { sayHello };
  },
};
</script>
<script setup>
import { ref } from "vue";

const message = ref("message");
</script>
<style></style>
