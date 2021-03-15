<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      :mobale-breakpoint="768"
      app
    >
      <v-img
      class="pa-3"
        src="texture.jpg"
        height="170"
      >
        <v-avatar size="120">
          <img
            src="avatar.jpg"
            alt="Dasha"
          >
        </v-avatar>
        <div class="avatar-name text-h4">Dasha</div>
      </v-img>
      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color=""
      flat
      dark
      src="night.jpg"
      prominent
      height="170"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
        ></v-img>
      </template>

      <v-container class="header-container pa-0">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-spacer />
          <search />
        </v-row>
        <v-row>
          <v-toolbar-title class="ml-4 text-h3 app-title">{{ $store.state.appTitle }}</v-toolbar-title>
        </v-row>
        <v-row>
          <live-date-time />
        </v-row>
      </v-container>
    </v-app-bar>
    <v-main>
      <router-view />
      <snackbar />
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      items: [
        { title: 'Todo', icon: 'mdi-format-list-checks', to: '/' },
        { title: 'About', icon: 'mdi-help-box', to: '/about' }
      ]
    }),
    mounted() {
      this.$store.dispatch('getTasks')
    },
    components: {
      'snackbar': require('@/components/Global/Snackbar.vue').default,
      'search': require('@/components/Tools/Search.vue').default,
      'live-date-time': require('@/components/Tools/LiveDateTime.vue').default,
    }
  }
</script>
<style lang="sass" scoped>
.app-title,  .avatar-name
  font-family: 'Tangerine', cursive !important
.header-container
  max-width: none
</style>