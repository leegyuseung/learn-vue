<template>
  <main>
    <div class="container py-4">
      <post-create @create-post="createPost"></post-create>
      <hr class="my-4" />
      <div class="row g-3">
        <div class="col col-4" v-for="post in posts" :key="post.id">
          <PostItem
            :title="post.title"
            :contents="post.contents"
            :type="post.type"
            :is-like="post.isLike"
            @toggle-like="post.isLike = !post.isLike"
            :obj="obj"
          />
          <!-- <button @click="post.isLike = !post.isLike">toggle</button> -->
        </div>
      </div>
      <hr class="my-4" />
      <!-- modelValue
      update:modelValue
      -->
      <!-- <LabelInput
        :model-value="username"
        @update:model-value="(value) => (username = value)"
      /> -->
      <LabelInput
        v-model="username"
        label="이름"
        class="parent-class"
        style="color: red"
        id="parent-id"
      />
      <!-- <LabelTitle v-model:title="username" label="제목" />
      <UserName
        v-model:firstname="firstname"
        v-model:lastname="lastname"
      ></UserName> -->
    </div>
  </main>
</template>

<script>
import { reactive, ref } from "vue";
import PostItem from "./PostItem.vue";
import PostCreate from "./PostCreate.vue";
import LabelInput from "./LabelInput.vue";
// import LabelTitle from "./LabelTitle.vue";
// import UserName from "./UserName.vue";

export default {
  components: {
    PostItem,
    PostCreate,
    LabelInput,
    // LabelTitle,
    // UserName,
  },
  setup() {
    const obj = reactive({
      title: "제목2",
      contents: "내용2",
    });
    const posts = reactive([
      { id: 1, title: "제목1", contents: "내용1", isLike: true, type: "news" },
      { id: 2, title: "제목2", contents: "내용2", isLike: true, type: "news" },
      { id: 3, title: "제목3", contents: "내용3", isLike: true, type: "news" },
      {
        id: 4,
        title: "제목4",
        contents: "내용4",
        isLike: false,
        type: "notice",
      },
      {
        id: 5,
        title: "제목5",
        contents: "내용5",
        isLike: false,
        type: "notice",
      },
    ]);
    const createPost = (newPost) => {
      console.log(newPost);
      posts.push(newPost);
    };

    const firstname = ref("");
    const lastname = ref("");
    const username = ref("");
    return { obj, posts, createPost, username, firstname, lastname };
  },
};
</script>

<style></style>
