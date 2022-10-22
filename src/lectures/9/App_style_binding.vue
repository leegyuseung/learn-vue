<template>
  <div :style="styleObject">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto est
    cupiditate consequatur. Culpa, eaque enim repudiandae inventore magnam
    repellendus. Nobis tempora voluptas fuga deserunt ipsam. Soluta fugit
    assumenda sed nam.
  </div>
  <button @click="fontSize--">-</button>
  <button @click="fontSize++">+</button>
</template>

<script>
import { computed, reactive, ref } from "vue";

export default {
  setup() {
    // const styleObject = reactive({
    //   color: "red",
    //   fontSize: "13px",
    // });
    const fontSize = ref(13);
    const styleObject = computed(() => {
      return {
        color: "red",
        fontSize: fontSize.value + "px",
      };
    });
    return { styleObject, fontSize };
  },
};
</script>

<style></style>
