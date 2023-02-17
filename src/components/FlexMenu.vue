<template>
  <div class="wrapper">
    <div
      class="boxes"
      :style="({ '--mouse-x': hoveredX }, { '--mouse-y': hoveredY })"
      @mousemove="mouseOver($event)"
      @mouseleave="mouseLeave()"
    >
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
      <div class="box">
        <div id="mouse"></div>
        <div class="innerbox"></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return { mouseX: 0, mouseY: 0 };
  },
  name: "FlexMenu",
  props: {},
  computed: {
    hoveredX: function () {
      return this.mouseX;
    },
    hoveredY: function () {
      return this.mouseY;
    },
  },
  methods: {
    mouseOver(e) {
      for (const box of document.getElementsByClassName("box")) {
        const rect = box.getBoundingClientRect();
        this.mouseX = e.clientX - rect.left;
        this.mouseY = e.clientY - rect.top;
        box.style.setProperty("--mouse-x", `${this.mouseX}px`);
        box.style.setProperty("--mouse-y", `${this.mouseY}px`);
      }
      console.log(this.mouseX);
    },
    mouseLeave() {
      for (const box of document.getElementsByClassName("box")) {
        box.style.setProperty("--mouse-x", `-1000px`);
        box.style.setProperty("--mouse-y", `-1000px`);
      }
    },
  },
  mounted() {},
};
</script>
<style scoped>
#mouse {
  border-radius: 100%;
  background-color: white;
  width: 10px;
  height: 10px;
  position: absolute;
  transform: translate(var(--mouse-x), var(--mouse-y));
  z-index: 3000;
  background: radial-gradient(
    800px circle at var(--mouse-x) var(--mouse-y),
    rgba(255, 255, 255, 0.981),
    transparent 40%
  );
  opacity: 0;
}
.wrapper {
  display: flex;
  overflow: hidden;
  padding: 0;
  margin: 0;
  height: 100vh;
  width: 100vw;
  justify-content: center;
}
.boxes {
  --mouse-x: -1000px;
  --mouse-y: -1000px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 8px;
  max-width: 916px;
  max-height: 316px;
  position: relative;
  margin: 0;
  padding: 0;
}
.box {
  display: flex;
  position: relative;
  border-radius: 10px;
  aspect-ratio: 1;
  width: 300px;
  padding: 0;
  margin: auto;
  opacity: 1;
  background-color: rgba(255, 255, 255, 0.145);
}
.box:before {
  position: absolute;
  top: 0px;
  left: 0px;
  content: "";
  width: 100%;
  height: 100%;
  background: radial-gradient(
    400px circle at var(--mouse-x) var(--mouse-y),
    rgba(255, 255, 255, 0.552),
    transparent 40%
  );
  border-radius: 10px;
}
.innerbox {
  border-radius: 10px;
  aspect-ratio: 1;
  background: rgb(0, 0, 0);
  width: calc(100% - 3px);
  opacity: 0.7;
  margin: auto;
}

.box:active {
  width: 297px;
  background-color: rgb(123, 123, 123);
}
</style>
