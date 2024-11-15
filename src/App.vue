<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Список любимых фильмов</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <MovieList />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import MovieList from './components/MovieList.vue';

export default {
  components: {
    MovieList,
  },
};
</script>

<style>
.text-center {
  text-align: center;
}
</style>
