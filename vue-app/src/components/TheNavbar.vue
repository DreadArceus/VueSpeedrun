<template>
  <div id="navbar">
    <router-link :to="{ name: 'HomePage' }" class="link">Home</router-link>
    <router-link :to="{ name: 'LoginPage' }" class="link">Login</router-link>
  </div>
</template>

<script>
export default {
  name: "TheNavbar",
};
</script>

<style>
#navbar {
  text-align: right;
  background-color: black;
  padding: 15px;
  margin: 0;
}
.link {
  margin-right: 6px;
  color: white;
}
</style>
