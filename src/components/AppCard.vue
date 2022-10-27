<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <!-- <p class="card-text" :class="$style.red"> -->
      <p class="card-text">
        Some quick example text to build on the card title and make up the bulk
        of the card's content.
      </p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
console.log("appcard module");
export default {
  setup() {
    // const style = useCssModule();
    // console.log(style);
    const color = ref("red");
    console.log("appcard setup");
    color.value = "yellow";
    return { color };
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
