<template>
  <div>
    <h2>보간법</h2>
    <p>{{ message }}</p>
    <!-- oncc로 인해 변경안됨 -->
    <p v-once>{{ message }}</p>
    <button @click="message = message + '!'">click</button>
    <hr />
    <h2>HTML</h2>
    <p>{{ rowHtml }}</p>
    <!-- html 그대로 출력한다. 조심해서사용해야한다(xss취약점) -->
    <p v-html="rowHtml"></p>
    <h2>속성바인딩</h2>
    <!-- v-bind는 자주사용한다. -->
    <div :title="dynamicTitle">마우스를 올려보세요</div>
    <input type="text" value="홍길동" :disabled="isInputDisabled" />
    <!-- 다중속성 바인딩 -->
    <input v-bind="attrs" />
    <h2>JavaScript</h2>
    <!-- javascript 이용가능 -->
    {{ message.split("").reverse().join("") }}<br />
    {{ isInputDisabled ? "예" : "아니오" }}
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const message = ref("안녕하세요");
    const rowHtml = ref("<strong>Hi</strong>");

    const dynamicTitle = ref("안녕하세요!");
    const isInputDisabled = ref(true);

    const attrs = ref({
      type: "text",
      value: "12345678",
      disabled: false,
    });
    return { attrs, message, rowHtml, dynamicTitle, isInputDisabled };
  },
};
</script>

<style></style>
