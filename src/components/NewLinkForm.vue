<template>
  <div class="form">
    <input
      class="input"
      type="text"
      name="url"
      v-model="originalUrl"
      :placeholder="placeholderText"
      autocomplete="off"
    />
    <button
      class="btn btn-default"
      @click="this.$emit('submit-link', this.originalUrl)"
      :disabled = '!isValid'
    >
      {{btnText}}
    </button>
  </div>
</template>

<script>
export default {
  name: "LinkForm",
  props: ['btnText', 'placeholderText'],
  data: () => {
    return {
      originalUrl: "",
    };
  },
  computed: {
    isValid() {
      // eslint-disable-next-line no-control-regex
      // const reg = new RegExp('https?://(www.)?[-a-zA-Z0-9@:%._+~#=]{1,256}.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_+.~#?&//=]*)');
      return (this.originalUrl.length > 0);
    }
  }
};
</script>

<style lang="scss">
@import "../assets/styles/style.scss";
</style>
