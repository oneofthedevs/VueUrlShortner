<template>
  <div class="container-div">
    <div class="Form">
      <NewLink
        @submit-link="onSubmit"
        :placeholderText="placeholder"
        :btnText="btn"
      />
    </div>
    <div class="data">
      <div class="row">
        <div class="text-col">
          <Clicks :click="23" />
        </div>
          <div class="graph-col">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Clicks from "../components/Clicks";
import NewLink from "../components/NewLinkForm";
export default {
  name: "Analytics",
  components: {
    Clicks,
    NewLink,
  },
  data: () => {
    return {
      response: null,
      placeholder: "e.g. http://localhost:5000/abr34",
      btn: "Get analytics",
    };
  },
  methods: {
    async onSubmit(url) {
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ url: url }),
      };
      const res = await fetch(
        "http://localhost:5000/analytics",
        requestOptions
      );
      this.response = await res.json();
    },
  },
};
</script>
<style lang="scss" scoped>
.Form {
  display: flex;
  justify-content: center;
  margin-top: 50px;
  width: 100%;
}
.row {
  margin: 20px 0 0 0;
  display: flex;
  justify-content: center;
}
.text-col {
  flex: 1;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
.graph-col {
  flex: 1;
}
</style>
