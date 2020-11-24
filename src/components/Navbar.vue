<template>
  <nav>
    <div class="container-div d-flex">
      <div class="titled-div">
        <h1><router-link :to="{name: 'Home'}" class="title">Lazy URL</router-link></h1>
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
  color: $darkSecondary;
}
.d-flex {
  display: flex;
}
.title {
  font-weight: 100;
  background: $darkSecondary;
  color: #fff;
  padding: 10px;
}
h1:hover {
  animation: flip 750ms forwards;
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
