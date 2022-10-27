<template>
  <main>
    <div class="container py-4">
      <div class="row g-3">
        <div class="col-4"><AppCardVue /></div>
        <div class="col-4"><AppCardVue /></div>
        <div class="col-4"><AppCardVue /></div>
        <div class="col-4"><AppCardVue /></div>
        <div class="col-4"><AppCardVue /></div>
        <div class="col-4"><AppCardVue /></div>

        <!-- <div class="col-4"><app-card-vue /></div> -->
      </div>
    </div>
  </main>
</template>

<script>
import AppCardVue from "./AppCard.vue";
export default {
  components: {
    AppCardVue,
  },
};
</script>

<style></style>
