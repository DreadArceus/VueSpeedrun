<template>
  <div id="navbar">
    <div id="left">
      <v-btn id="drawer-btn" icon color="secondary">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </div>
    <div id="right">
      <router-link :to="{ name: 'HomePage' }">
        <v-btn text color="secondary">
          Home
        </v-btn>
      </router-link>
      <router-link :to="{ name: 'LoginPage' }">
        <v-btn text color="secondary">
          Login
        </v-btn>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheNavbar",
};
</script>

<style>
#navbar {
  padding: 15px;
  padding-bottom: 55px;
}
#left {
  float: left;
}
#right {
  float: right;
}
</style>
