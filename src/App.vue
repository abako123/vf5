<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"/>
      <site-title :title="title"></site-title>
      <v-spacer/>

      <v-btn icon to="/xxx">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon to="/about">
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon to="/">
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>

      <site-menu></site-menu>
    </v-navigation-drawer>

    <v-main>
      <router-view></router-view>
    </v-main>

    <site-footer :footer="footer"></site-footer>

  </v-app>
</template>

<script>
import SiteTitle from '@/views/site/SiteTitle'
import SiteFooter from '@/views/site/SiteFooter'
import SiteMenu from '@/views/site/SiteMenu'

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
