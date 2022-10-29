<template>
  <div class="row g-3">
    <div class="col col-2">
      <!-- @click="$emit('createPost', 1, 2, 3, '김길동')" -->
      <select
        v-model="type"
        class="form-control"
        id="exampleFormControlSelect1"
      >
        <option value="news">news</option>
        <option value="notice">notice</option>
      </select>
    </div>
    <div class="col col-8">
      <input type="text" class="form-control" v-model="title" />
    </div>
    <div class="col col-2 d-grid">
      <button @click="createPost" class="btn btn-primary">추가</button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  emits: {
    // createPost: null, <-유효성검사없을시
    createPost: (newPost) => {
      console.log(newPost);
      if (!newPost.type) {
        return false;
      } else if (!newPost.title) {
        return false;
      }
      return true;
    },
  },
  // emits: ["createPost"],
  setup(props, { emit }) {
    const type = ref("news");
    const createPost = () => {
      const newPost = {
        type: type.value,
        title: title.value,
      };
      emit("createPost", newPost);
      type.value = "news";
      title.value = "";
    };
    const title = ref("");
    return { createPost, title, type };
  },
};
</script>

<style></style>
