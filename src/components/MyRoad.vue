<template>
  <div class="road">
    <div class="rail"></div>
    <div class="left-line"></div>
    <div class="right-line"></div>
  </div>
</template>

<style scoped>
.road {
  position: relative;
  height: 100vh;
  width: 300px;
  background: gray;
}
.rail {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%);
  background-image: url('~assets/rail.png');
  background-repeat: repeat-y;
  background-size: contain;
  height: 100vh;
  width: 64px;
}
.left-line {
  position: absolute;
  left: 21%;
  transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
  -ms-transform: translateX(-50%);
  background-image: url('~assets/line.png');
  background-repeat: repeat-y;
  background-size: contain;
  height: 100vh;
  width: 10px;
}
.right-line {
  position: absolute;
  right: 21%;
  transform: translateX(50%);
  -webkit-transform: translateX(50%);
  -ms-transform: translateX(50%);
  background-image: url('~assets/line.png');
  background-repeat: repeat-y;
  background-size: contain;
  height: 100vh;
  width: 10px;
}
</style>
