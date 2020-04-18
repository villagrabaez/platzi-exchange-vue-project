<template>
  <button
    v-on:click="buttonClick"
    class="bg-trasnparent hover:bg-green-500 text-green-700 font-semibold hover:text-white py- px-2 border border-green-500 hover:border-transparent rounded"
  >
    <beat-loader :loading="isLoading" :color="'#68d391'" :size="8" />
    <span v-show="!isLoading">
      <slot></slot>
    </span>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  props: {
    isLoading: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    buttonClick() {
      this.$emit("custom-click");
    }
  }
};
</script>
