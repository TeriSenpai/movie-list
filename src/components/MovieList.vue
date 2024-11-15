<template>
  <v-container>
    <v-row class="justify-center">
      <v-col cols="12" md="8">
        <v-text-field
          label="Введите название фильма"
          v-model="newMovie"
          @keyup.enter="addMovie"
          outlined
          color="primary"
        />
        <v-btn color="primary" @click="addMovie">Добавить фильм</v-btn>
      </v-col>
    </v-row>

    <v-row>
      <v-col
        v-for="(movie, index) in movies"
        :key="index"
        cols="12"
        sm="6"
        md="4"
      >
        <v-card class="movie-card" elevation="3">
          <v-img
            src="https://placeimg.com/640/480/movie"
            height="200px"
          ></v-img>
          <v-card-title class="movie-title">{{ movie }}</v-card-title>
          <v-card-actions>
            <v-btn color="error" text @click="removeMovie(index)">
              Удалить
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      newMovie: "",
      movies: ["Интерстеллар", "Начало", "Матрица"],
    };
  },
  methods: {
    addMovie() {
      if (this.newMovie.trim()) {
        this.movies.push(this.newMovie.trim());
        this.newMovie = "";
      }
    },
    removeMovie(index) {
      this.movies.splice(index, 1);
    },
  },
};
</script>

<style scoped>
.movie-card {
  margin-top: 20px;
  border-radius: 10px;
  overflow: hidden;
}
.movie-title {
  font-weight: bold;
  color: #424242;
  font-size: 1.25rem;
}
</style>
