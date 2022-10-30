<template>
  <main>
    <div class="container py-4">
      <!-- @click="sayHello" -->
      <MyButton class="my-button" id="my-button" @click="sayHello"></MyButton>
      <LabelInput label="이름" data-id="id입니다." />
    </div>
  </main>
</template>

<script>
import LabelInput from "./LabelInput.vue";
import MyButton from "./MyButton.vue";

export default {
  components: { MyButton, LabelInput },
  setup() {
    const sayHello = () => {
      alert("안녕");
    };
    return { sayHello };
  },
};
</script>

<style></style>
