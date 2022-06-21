<template>
  <div class="d-flex justify-center wrap">
    <MyRoad />
    <TraficLight :top="64" :state="state" />
  </div>
</template>

<script>
import moment from 'moment'
import 'moment/locale/ja'
moment.locale('ja')

export default {
  data() {
    return {
      state: 0,
    }
  },
  mounted() {
    const current = moment()
    const begin = moment().hour(0).minute(0).seconds(44)
    console.log(current)
    console.log(begin)
    console.log(current.diff(begin))
    // setInterval(() => {
    //   const current = moment()
    //   const begin = moment().hour(0).minute(0).seconds(44)
    //   console.log(current)
    //   console.log(begin)
    //   console.log(begin.diff(current))

    //   this.state += 1
    //   if (this.state > 2) {
    //     this.state = 0
    //   }
    //   // console.log(this.state)
    // }, 1000)
  },
}
</script>

<style scoped>
.wrap {
  position: relative;
}
</style>
