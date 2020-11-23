<template>
  <nav>
    <div class="container-div">
      <div class="titled-div">
        <h1 class="title"><router-link :to="{name: 'Home'}" class="title">Lazy URL</router-link></h1>
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
  // background: $primary;
  color: $darkSecondary;
}
.title {
  font-weight: 100;
  color: $darkSecondary;
}
.container-div {
  display: flex;
  margin:0 5%;
  padding-top: 10px;
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
  color: $darkSecondary;
  padding: 10px 15px;
  border-bottom: 4px solid transparent;

}
.nav-link:hover {
  border-bottom: 4px solid $darkSecondary;
}
</style>
