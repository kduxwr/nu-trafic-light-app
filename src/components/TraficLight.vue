<template>
  <div class="trafic-light" :style="posStyle">
    <div class="trafic-light-inner">
      <div class="blue" :style="blueStyle"></div>
      <div class="yellow" :style="yellowStyle"></div>
      <div class="red" :style="redStyle"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    top: Number,
    state: Number,
  },
  computed: {
    posStyle() {
      return `top: ${this.top}px`
    },
    blueStyle() {
      if (this.state !== 0) {
        return 'background-color: gray !important;'
      } else {
        return ''
      }
    },
    yellowStyle() {
      if (this.state !== 1) {
        return 'background-color: gray !important;'
      } else {
        return ''
      }
    },
    redStyle() {
      if (this.state !== 2) {
        return 'background-color: gray !important;'
      } else {
        return ''
      }
    },
  },
}
</script>

<style scoped>
.trafic-light {
  position: absolute;
  width: 150px;
  height: 60px;
  border-radius: 60px;
  border: 1px solid black;
  background-color: rgb(236, 236, 236);
}
.trafic-light-inner {
  position: relative;
  width: 100%;
  height: 60px;
}
.blue {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  -webkit-transform: translateY(-50%);
  -ms-transform: translateY(-50%);
  left: 10px;
  /* transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%); */
  height: 40px;
  width: 40px;
  background-color: blue;
  border-radius: 40px;
  /* border: 1px solid gray; */
}
.yellow {
  position: absolute;
  top: 50%;
  left: 54px;
  /* transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%); */
  transform: translateY(-50%);
  -webkit-transform: translateY(-50%);
  -ms-transform: translateY(-50%);

  height: 40px;
  width: 40px;
  background-color: yellow;
  border-radius: 40px;
  /* border: 1px solid black; */
}
.red {
  position: absolute;
  top: 50%;
  right: 10px;
  /* transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%); */
  transform: translateY(-50%);
  -webkit-transform: translateY(-50%);
  -ms-transform: translateY(-50%);

  height: 40px;
  width: 40px;
  background-color: red;
  border-radius: 40px;
  /* border: 1px solid gray; */
}
</style>
