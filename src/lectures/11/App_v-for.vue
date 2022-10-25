<template>
  <div>
    <ul>
      <template v-for="(item, index) in evenItems" :key="item.id">
        <!-- <li v-if="item.id % 2 === 0"> -->
        <li>{{ item.id }}{{ index }}{{ item.message }}</li>
      </template>
    </ul>
    <hr />
    <ul>
      <li v-for="(value, key, index) in myObject" :key="key">
        {{ index }}-{{ key }}-{{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import { computed, reactive } from "vue";

export default {
  setup() {
    const items = reactive([
      { id: 1, message: "Java" },
      { id: 2, message: "HTML" },
      { id: 3, message: "CSS" },
      { id: 4, message: "JavaScript" },
    ]);
    // 짝수만 불러오기
    const evenItems = computed(() => items.filter((item) => item.id % 2 === 0));

    const myObject = reactive({
      title: "제목",
      author: "홍길동",
      pbulishedAt: "2016-01-01",
    });
    return { items, evenItems, myObject };
  },
};
</script>

<style></style>
