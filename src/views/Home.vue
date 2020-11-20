<template>
  <div class="home">
    <div class="main-section">
      <div class="form">
      <input class="input" type="text" name="url" v-model="originalUrl" placeholder="e.g. http://www.google.com" autocomplete="off">
      <button class="btn btn-default" @click="submit">Click to shorten</button>
      </div>
    </div>
    <div class="generated" v-if="response">
      <span>Generated Link: </span><a class="link" :href="response.response.shortUrl" target="_blank">{{response.response.shortUrl}}</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data: () => {
    return {
      originalUrl: '',
      response: null
    }
  },
  methods: {
    async submit() {
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ url: this.originalUrl })
      };
      const res = await fetch('http://localhost:5000/generateURL', requestOptions);
      const data = await res.json()
      
      this.response = data;
      console.log(this.response.response.shortUrl);
    }
  }
}
</script>

<style lang="scss" scoped>
.home{ 
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.main-section {
  display: flex;
}
.form {
  flex-basis: 1000px;
}

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
  // outline: 1px solid #FFAC53;
}

.generated{
  margin-top: 20px;
  font-size: 15px;
}

.link {
  display: inline;
  text-decoration: none;
  font-size: 17px;
  color: #3e3e3e;
  background: #FFAC53;
  padding: 10px 20px;
  color: #fff;
  border-radius: 5px;
}

.btn {
  padding: 10px 20px;
  border: 0;
  cursor: pointer;
  border-radius: 5px;
}

.btn-default {
  border: 2px solid #FFAC53;
  background: #FFAC53;
  color: #fff;
}

</style>