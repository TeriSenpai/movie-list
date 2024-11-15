<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Список любимых фильмов</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text @click="goHome">Домой</v-btn>
    </v-app-bar>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  methods: {
    goHome() {
      this.$router.push({ name: 'Home' });
    },
  },
};
</script>
