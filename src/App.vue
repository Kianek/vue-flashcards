<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title>Flashy Cards</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
import Dashboard from "./views/Dashboard";

export default {
  name: "App",
  components: {
    Dashboard
  },
  data: () => ({
    //
  })
};
</script>
