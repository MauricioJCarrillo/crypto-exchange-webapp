<template>
  <button
    v-on:click="buttonClick"
    class="bg-transparent hover:bg-green-200 text-green-700 font-semibold hover:text-white py-2 px-2 border border-green-500 hover:border-transparent rounded-md"
  >
    <beat-loader :color="'#68d391'" :loading="isLoading" :size="8" />
    <slot v-if="!isLoading"></slot>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  props: {
    isLoading: {
      type: Boolean,
      default: false,
    },
  },

  methods: {
    buttonClick() {
      this.$emit("custom-click");
    },
  },
};
</script>
