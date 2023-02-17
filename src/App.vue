<template>
  <FlexMenu class="menu" />
</template>

<script>
import FlexMenu from "./components/FlexMenu.vue";

export default {
  name: "App",
  components: { FlexMenu },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu {
  width: 916px;
  height: 316px;
}
</style>
