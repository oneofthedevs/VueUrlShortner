<template>
  <nav>
    <div class="container-div">
      <div class="titled-div">
        <h1 class="title">lazy URL</h1>
      </div>
      <div class="navigation-div">
        <ul class="nav-links">
          <li class="nav-item"><router-link :to="{name: 'Home'}" class="nav-link">Home</router-link></li>
          <li class="nav-item"><router-link :to="{name: 'Analytics'}" class="nav-link">Analytics</router-link></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style  lang="scss" scoped>
@import '../assets/styles/style.scss';

nav{
  width: 100%;
  background: $orange;
}
title {
  margin: 10px 0;
}
.container-div {
  margin: 0 5%;
  display: flex;
}
.navigation-div {
  display: flex;
  justify-content: center;
  align-items: center;
}
.titled-div {
  display: flex;
  align-items: center;
  flex: 1;
}
.nav-links {
  display: flex;
  flex-wrap: nowrap;
}
.nav-item {
  display: flex;
}
.nav-link {
  text-decoration: none;
  color: #fff;
  padding: 10px 15px;
  border-bottom: 4px solid transparent;

}
.nav-link:hover {
  border-bottom: 4px solid darkorange;
}
</style>
