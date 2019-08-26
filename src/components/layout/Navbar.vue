<template>
  <v-app-bar app>
    <!-- Only show the nav icon when the user is logged in -->
    <v-app-bar-nav-icon></v-app-bar-nav-icon>
    <v-toolbar-title to="/">
      <router-link to="/" tag="span" style="cursor: pointer">Flashy Cards</router-link>
    </v-toolbar-title>

    <v-spacer class="hidden-sm-and-down"></v-spacer>

    <v-toolbar-items>
      <v-btn depressed to="/register">Register</v-btn>
      <v-btn depressed to="/login">Log In</v-btn>
    </v-toolbar-items>
  </v-app-bar>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
</style>