<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      temporary
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer />
      <v-toolbar-title class="text-h4">{{ time }} </v-toolbar-title>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer fixed app class="d-flex justify-center">
      <span>&copy; 2022 IKEHARA Haruto.</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '電車通り信号機アプリ',
      timerID: null,
      time: '',
    }
  },
  mounted() {
    this.updateTime()
    this.timerID = setInterval(this.updateTime, 1000)
  },
  methods: {
    updateTime() {
      const currentDate = new Date()
      this.time =
        this.zeroPadding(currentDate.getHours(), 2) +
        ':' +
        this.zeroPadding(currentDate.getMinutes(), 2) +
        ':' +
        this.zeroPadding(currentDate.getSeconds(), 2)
    },
    zeroPadding(num, len) {
      let zero = ''

      // 0の文字列を作成
      for (let i = 0; i < len; i++) {
        zero += '0'
      }

      // zeroの文字列と、数字を結合し、後ろ２文字を返す
      return (zero + num).slice(-len)
    },
  },
}
</script>
