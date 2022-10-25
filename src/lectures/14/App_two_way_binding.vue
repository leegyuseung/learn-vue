<template>
  <div>
    <h2>input value</h2>
    <!-- <input type="text" v-model="inputValue" /> -->

    <!-- lazy를 사용하면 focus가 사라지면 동기화된다. -->
    <!-- <input type="text" v-model.lazy="inputValue" /> -->

    <!-- number를 이용하면 숫자스트링을 넘버로 바꿔준다. -->
    <!-- <input type="text" v-model.number="inputValue" /> -->

    <!-- 공백을 지워준다. -->
    <input type="text" v-model.trim="inputValue" />

    <!-- :value="inputValue"
      @input="(event) => (inputValue = event.target.value)" -->
    <div>{{ inputValue }}</div>
    <div>{{ typeof inputValue }}</div>

    <h2>textarea value</h2>
    <textarea v-model="textareaValue"></textarea>
    <!-- :value="textareaValue"
    @input="(event) => (textareaValue = event.target.value)" -->
    <div>{{ textareaValue }}</div>

    <h2>checkbox value</h2>
    <label for="checkbox">{{ checkboxValue }}</label>
    <input
      type="checkbox"
      id="checkbox"
      v-model="checkboxValue"
      true-value="yes"
      false-value="no"
    />
    <h3>checkbox values</h3>
    <label
      ><input
        type="checkbox"
        value="html"
        v-model="checkboxValues"
      />HTML</label
    >
    <label
      ><input type="checkbox" value="css" v-model="checkboxValues" />CSS</label
    >
    <label
      ><input
        type="checkbox"
        value="javascript"
        v-model="checkboxValues"
      />JS</label
    >

    <!-- :checked="checkboxValue"
      @change="(event) => (checkboxValue = event.target.checked)" -->

    <h2>radio value</h2>
    <label for="">
      <input type="radio" name="type" value="O" v-model="radioValue" />
      <!-- :checked="radioValue === 'O'"
        @change="(event) => (radioValue = event.target.value)" -->
      O형
    </label>
    <label for="">
      <input type="radio" name="type" value="A" v-model="radioValue" />
      <!-- :checked="radioValue === 'A'"
        @change="(event) => (radioValue = event.target.value)" -->
      A형
    </label>
    <div>{{ radioValue }}</div>

    <h2>select value</h2>
    <!-- :value="selectValue"
    @change="(event) => (selectValue = event.target.value)" -->
    <select v-model="selectValue">
      <option value="html">HTML</option>
      <option value="css">CSS</option>
      <option value="javascript">JS</option>
    </select>
    <div>{{ selectValue }}</div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const inputValue = ref(null);
    const textareaValue = ref(null);
    const checkboxValue = ref("yes");
    const checkboxValues = ref([]);
    const radioValue = ref("O");
    const selectValue = ref("html");
    return {
      inputValue,
      textareaValue,
      checkboxValue,
      radioValue,
      selectValue,
      checkboxValues,
    };
  },
};
</script>

<style></style>
