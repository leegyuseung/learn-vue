<template>
  <div>
    <p>author:{{ author }}</p>
    <p>title:{{ title }}</p>
  </div>
</template>

<script>
import { reactive, toRef, toRefs } from "vue";

export default {
  setup() {
    const book = reactive({
      author: "vue team",
      year: "2020",
      title: "vue3",
      description: "read a book",
      price: "free",
    });
    // 구조분해할당을하면 반응성을 잃어버린다.
    // const { author, title } = book;
    // 구조분해할당을 가능하게하려면 toRef(하나만 가져오기), toRefs를 사용해야한다.
    const year = toRef(book, "year");
    const { author, title } = toRefs(book);

    return { author, title, book, year };
  },
};
</script>

<style></style>
