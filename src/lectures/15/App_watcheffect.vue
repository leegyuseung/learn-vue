<template>
  <div>
    <form @submit.prevent="save(title, contents)" action="">
      <input type="text" v-model.lazy="title" placeholder="Title" />
      <textarea v-model.lazy="contents" placeholder="Contents"></textarea>
      <hr />
      <button>저장</button>
    </form>
  </div>
</template>

<script>
import { ref, watchEffect } from "vue";

export default {
  setup() {
    const title = ref("");
    const contents = ref("");

    const save = (title, contents) => {
      console.log(`저장되었습니다. title:${title}, contents:${contents}`);
    };

    // watch와 다르게 최초로 즉시 실행된다.
    watchEffect(() => {
      console.log("watchEffect");
      console.log(title.value);
      console.log(contents.value);
      save(title.value, contents.value);
    });
    return { title, contents, save };
  },
};
</script>

<style></style>
