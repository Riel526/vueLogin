<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
      v-for="link in links"
      :key="`${link.label}header-link`" 
      rounded 
      text 
      :to="link.url">
      {{ link.label }}
      </v-btn>
    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>

    <v-footer class="primary lighten-1">
      <v-layout justify-center wrap>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          class="my-2"
          color="white"
          text
          rounded
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-col class="text-center mt-4" cols="12" dark>
          Dashboard
        </v-col>
      </v-row>
    </v-layout>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    showPassword: false,
    links: [
      {
        label: 'Home',
        url: '/'
      },
      {
        label: 'Login',
        url: '/login'
      },
      {
        label: 'Dashboard',
        url: "/dashboard"
      }
    ]
  }),
};
</script>
