<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"/>
      <site-title :title="title"></site-title>
      <v-spacer/>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer">
      <v-divider></v-divider>
      <site-menu></site-menu>
    </v-navigation-drawer>

    <v-main>
      <router-view/>
    </v-main>

    <site-footer :footer="footer"></site-footer>
  </v-app>
</template>

<script>
import SiteTitle from './components/title'
import SiteFooter from './components/footer'
import SiteMenu from './components/menu'

export default {
  components: { SiteTitle, SiteFooter, SiteMenu },
  name: 'App',
  data () {
    return {
      drawer: false,
      items: [],
      title: '나의 타이틀입니다',
      footer: 'ABAKO-Simsan'
    }
  },
  mounted () {
  }
}
</script>
