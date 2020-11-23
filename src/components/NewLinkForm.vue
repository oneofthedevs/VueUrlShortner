<template>
    <div class="form">
      <input class="input" type="text" name="url" v-model="originalUrl" placeholder="e.g. https://www.google.com" autocomplete="off">
      <button class="btn btn-default" @click="onSubmit">Click to shorten</button>
    </div>
</template>

<script>
export default {
name: 'LinkForm',
data: () => {
  return {
    originalUrl: ''
  }
},
methods: {
  onSubmit() {
    this.$emit('generate-link', this.originalUrl);
  }
}
}
</script>

<style lang="scss">
@import '../assets/styles/style.scss';

.input[type=text] {
  flex: 1;
  padding: 10px 20px;
  background: #eee;
  border: 0;
  border-radius: 5px;
  border: 2px solid transparent;
  margin: {
    right: 5px
  };
}

.input[type=text]:focus {
  border: 2px solid #FFAC53;
  /* // outline: 1px solid #FFAC53; */
}
</style>