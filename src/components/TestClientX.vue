<template>
  <div class="test" @click="testing($event)"></div>
</template>
<script>
export default {
  data() {
    return {};
  },
  name: "TestClientX",
  props: {},
  methods: {
    testing(event) {
      console.log(event.clientX);
      console.log(event.pageX);
    },
  },
};
</script>
<style scoped>
.test {
  width: 100px;
  height: 100px;
  outline: 5px solid white;
  display: flex;
  translate: (50%, 50%);
}
</style>
