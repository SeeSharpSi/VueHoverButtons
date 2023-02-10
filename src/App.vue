<template>
  <FlexMenu />
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
</style>
