<template>
  <div class="form">
    <input
      class="input"
      type="text"
      name="url"
      v-model="originalUrl"
      placeholder="e.g. https://www.google.com"
      autocomplete="off"
    />
    <button
      class="btn btn-default"
      @click="this.$emit('generate-link', this.originalUrl)"
    >
      Click to shorten
    </button>
  </div>
</template>

<script>
export default {
  name: "LinkForm",
  data: () => {
    return {
      originalUrl: "",
    };
  },
};
</script>

<style lang="scss">
@import "../assets/styles/style.scss";
</style>
