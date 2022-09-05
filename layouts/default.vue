<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      clipped
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      clipped-left
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      drawer: false,
      items: [
        {
          title: 'Home',
          to: '/'
        },{
          title: 'Kings Fall',
          to: '/kf'
        },
        {
          title: 'Vow of the Disciple',
          to: '/vod'
        },
        {
          title: 'Vault of Glass',
          to: '/vog'
        },
        {
          title: 'Deep Stone Crypt',
          to: '/dsc'
        },
        {
          title: 'Garden of Salvation',
          to: '/gos'
        },
        {
          title: 'Last Wish',
          to: '/lw'
        }
      ],
      title: 'D2RS'
    }
  }
}
</script>
