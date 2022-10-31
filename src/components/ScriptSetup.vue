<template>
  <div class="container py-4">
    {{ msg }} <button @click="sayHello">click</button>
    <input type="text" v-model="message" />
    <PostItem
      type="news"
      title="제목"
      contents="내용"
      :is-like="true"
    ></PostItem>
    <hr />
    <TemplateRefsChild ref="child"></TemplateRefsChild>
    <template v-if="child">{{ child.message }} </template>
    <hr />
    <MyButton class="parent-class"></MyButton>
  </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";
import PostItem from "@/components/setup/PostItem.vue";
import TemplateRefsChild from "./setup/TemplateRefsChild.vue";
import MyButton from "./setup/MyButton.vue";

const message = ref("");
const msg = "Hello World!";
const sayHello = () => {
  alert("hello world");
};

const child = ref(null);

defineExpose({
  msg,
});

// const response = await axios(
//   "http://dummy.restapiexample.com/api/v1/employees"
// );
// console.log(response);

async function callApi() {
  const response = await axios(
    "http://dummy.restapiexample.com/api/v1/employees"
  ).then((response) => {
    console.log(response);
  });
}
callApi();
</script>

<style lang="scss" scoped></style>
