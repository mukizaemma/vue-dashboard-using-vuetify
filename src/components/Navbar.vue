<template>
  <nav>
    <v-app-bar color="green" dark app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"> </v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase">
        <span class="font-weight-light">Ezee </span>
        <span>Techs</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn text v-on="on">
            <v-icon left>exapand more</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list-item
          v-for="link in links"
          :key="link.text"
          router
          :to="link.route"
          active-class="border"
        >
          <v-list-item-title>{{ link.text }}</v-list-item-title>
        </v-list-item>
      </v-menu>
      <v-btn>
        <span>Exit</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" dark app class="green darken-4">
      <v-layout column align-center>
        <v-flex class="mt-5">
          <v-avatar size="100">
            <v-img src="ezeetech.jpg" />
          </v-avatar>
          <p class="white--text subheding mt-5 text-center">UserName</p>
        </v-flex>
      </v-layout>
      <v-flex class="mt-4 mb-4">
        <popup />
      </v-flex>
      <v-list flat>
        <v-list-item
          v-for="link in links"
          :key="link.text"
          router
          :to="link.route"
          active-class="border"
        >
          <v-list-item-action>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
import Popup from "./Popup.vue";
export default {
  data: () => ({
    drawer: true,
    links: [
      { icon: "dashboard", text: "Dashboard", route: "/" },
      { icon: "folder", text: "My Project", route: "/project" },
      { icon: "person", text: "Team", route: "/team" },
      { icon: "person", text: "Members", route: "/members" },
    ],
  }),
  components: {
    Popup,
  },
};
</script>

<style scoped>
.border {
  border-left: 4px solid #0ba518;
}
</style>
