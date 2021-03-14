<template>
  <v-app>
    <v-main id="main">
      <div class="header sticky" ref="navbar">
        <the-navbar />
      </div>
      <v-container fluid id="base" :style="offsetStyle">
        <router-view />
      </v-container>
    </v-main>
    <!-- <v-footer app> -->
    <!-- </v-footer> -->
  </v-app>
</template>

<script>
import TheNavbar from "./components/TheNavbar.vue";
export default {
  components: { TheNavbar },
  name: "App",
  methods: {
    updateOffset() {
      this.offset = this.$refs.navbar.clientHeight + "px";
    },
  },
  data() {
    return {
      offset: "0px",
    };
  },
  computed: {
    offsetStyle() {
      return {
        transform: `translateY(${this.offset})`,
        minHeight: `calc(100vh - ${this.offset})`,
      };
    },
  },
  mounted() {
    this.updateOffset();
    window.addEventListener("resize", this.updateOffset);
  },
  unmounted() {
    window.removeEventListener("resize", this.updateOffset);
  },
};
</script>

<style>
.sticky {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  background-color: black;
}
#base {
  background-color: #2c3e50;
  color: white;
}
#main {
  overflow: auto;
}
html {
  scrollbar-width: none;
}
html::-webkit-scrollbar {
  display: none;
}
</style>
