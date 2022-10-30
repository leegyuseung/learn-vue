<template>
  <div class="card">
    <div class="card-body">
      <span class="badge bg-secondary">{{ typeName }}</span>
      <h5 class="card-title mt-2">{{ title }}</h5>
      <!-- <p class="card-text" :class="$style.red"> -->
      <p class="card-text">
        {{ contents }}
      </p>
      <a href="#" class="btn" :class="isLikeClass">좋아요</a>
      <br />
    </div>
  </div>
</template>

<script>
import { computed, ref } from "vue";
console.log("appcard module");
export default {
  props: {
    type: {
      type: String,
      default: "news",
      validator: (value) => {
        return ["news", "notice"].includes(value);
      },
    },
    title: {
      type: String,
      required: true,
    },
    contents: {
      type: String,
      // required: true,
    },
    isLike: {
      type: Boolean,
      default: false,
    },
    obj: {
      type: Object,
      default: () => {},
    },
  },
  emits: ["toggleLike"],
  setup(props, context) {
    console.log("props.title", props.title);
    const isLikeClass = computed(() =>
      props.isLike ? "btn-danger" : "btn-outline-danger"
    );
    const typeName = computed(() =>
      props.type === "news" ? "뉴스" : "공지사항"
    );
    const toggleLike = () => {
      context.emit("toggleLike");
    };
    // const style = useCssModule();
    // console.log(style);
    const color = ref("red");
    console.log("appcard setup");
    color.value = "yellow";
    return { color, isLikeClass, typeName, toggleLike };
  },
};
</script>
<style moudule>
.red {
  color: v-bind(color) !important;
}
</style>

<!-- <style scoped>
.red {
  color: red !important;
}
</style> -->

<!-- <style module="classes">
.red {
  color: red !important;
}
</style> -->
