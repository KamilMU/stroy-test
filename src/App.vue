<template>
  <div class="app">
    <Header />
    <Menu />
  </div>
</template>

<script>
import Menu from "./components/Menu.vue";
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
    Menu,
  },
};
</script>

<style lang="scss">
img {
  max-width: 100%;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}

.app {
  font-family: "Open Sans";
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.content {
  width: 100%;
  max-width: 1110px;
  margin: 0 auto;
}
</style>
