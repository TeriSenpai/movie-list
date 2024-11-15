<template>
    <v-container>
      <h1 class="page-title">Список фильмов</h1>
      <v-row>
        <v-col
          v-for="(movie, index) in movies"
          :key="index"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card class="movie-card" @click="goToDetails(movie.id)">
            <v-img
              src="https://placeimg.com/640/480/movie"
              height="200px"
            ></v-img>
            <v-card-title class="movie-title">{{ movie.title }}</v-card-title>
          </v-card>
        </v-col>
      </v-row>
      <v-btn color="primary" @click="goToAddMovie" class="add-movie-btn">Добавить фильм</v-btn>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'HomePage',
    computed: {
      movies() {
        return this.$store.getters.allMovies; // Получаем фильмы из хранилища
      },
    },
    methods: {
      goToDetails(id) {
        this.$router.push({ name: 'MovieDetails', params: { id } });
      },
      goToAddMovie() {
        this.$router.push({ name: 'AddMovie' });
      },
    },
  };
  </script>
  
  <style scoped>
  .page-title {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: #424242;
  }
  
  .movie-card {
    margin-top: 20px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out;
  }
  
  .movie-card:hover {
    transform: scale(1.05);
  }
  
  .movie-title {
    font-weight: bold;
    color: #424242;
    font-size: 1.25rem;
  }
  
  .add-movie-btn {
    display: block;
    margin: 30px auto;
    padding: 10px 20px;
    font-size: 1.2rem;
  }
  </style>
  