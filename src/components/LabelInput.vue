<template>
  <label class="form-label" id="child-id">
    {{ label }}
    <!-- v-model:'username' -->
    <!-- <input
      type="text"
      :value="modelValue"
      @input="(event) => $emit('update:modelValue', event.target.value)"
      /> -->
  </label>

  <input type="text" v-bind="$attrs" v-model="value" class="form-control" />
</template>

<script>
import { computed } from "vue";

export default {
  props: ["modelValue", "label"],
  emits: ["update:modelValue"],
  setup(props, { emit }) {
    const value = computed({
      get() {
        return props.modelValue;
      },
      set(value) {
        emit("update:modelValue", value);
      },
    });
    return { value };
  },
};
</script>

<style></style>
