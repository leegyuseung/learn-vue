<template>
  <div>
    <TheNav></TheNav>
    <TheVue></TheVue>
    <AppCard></AppCard>
  </div>
</template>

<script>
import AppCard from "./src/components/AppCard.vue";
import TheNav from "./src/components/TheNav.vue";
import TheVue from "./src/components/TheVue.vue";

export default {
  components: { TheVue, TheNav, AppCard },
  setup() {},
};
</script>

<style></style>
