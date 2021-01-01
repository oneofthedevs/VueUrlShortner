<template>
  <div class="home">
    <div class="main-section">
      <LinkForm
        @submit-link="submit"
        :placeholderText="placeholder"
        :btnText="btn"
      />
    </div>
    <div class="generated" v-if="response">
      <span>Generated Link: </span
      ><a class="link" :href="response.response.shortUrl" target="_blank">{{
        response.response.shortUrl
      }}</a>
    </div>
  </div>
</template>

<script>
import LinkForm from "../components/NewLinkForm";
export default {
  name: "Home",
  components: {
    LinkForm,
  },
  data: () => {
    return {
      originalUrl: "",
      response: null,
      placeholder: "e.g. https://www.google.com",
      btn: "Click to shorten",
    };
  },
  methods: {
    async submit(url) {
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ url: url }),
      };
      const res = await fetch(
        "http://localhost:5000/generateURL",
        requestOptions
      );
      this.response = await res.json();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/styles/style.scss";

.home {
  min-height: calc(100vh - 100px);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.main-section {
  width: 100%;
  display: flex;
  justify-content: center;
}
.form {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  width: 90%;
}

.generated {
  margin-top: 20px;
  font-size: 15px;
}

.link {
  display: inline;
  text-decoration: none;
  font-size: 17px;
  background: $darkSecondary;
  padding: 10px 20px;
  color: #fff;
  border-radius: 5px;
}
</style>
