<template>
  <div class="app">
    <VNavigation />
    <router-view />
  </div>
</template>

<script>
import VNavigation from "./components/VNavigation.vue";

export default {
  name: "App",
  components: {
    VNavigation,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Mouse+Memoirs&family=Raleway:wght@400;500&display=swap");

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Raleway", sans-serif;
  font-weight: 400;
}

body {
  overflow-y: scroll;
}

.app {
  min-height: 100vh;
  position: relative;
  background-color: rgb(62, 61, 61);
  color: #fff;
}

.container {
  padding: 0 20px;
  max-width: 1140px;
  margin: 0 auto;
}

.about,
.portfolio,
.contact {
  padding-top: 6rem;
  text-align: center;
}
</style>
