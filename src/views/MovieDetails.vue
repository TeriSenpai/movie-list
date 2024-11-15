<template>
    <v-container>
      <h1 class="page-title">Детали фильма</h1>
      <v-card class="movie-details-card">
        <v-img
          src="https://placeimg.com/640/480/movie"
          height="300px"
        ></v-img>
        <v-card-title class="movie-title">{{ movieTitle }}</v-card-title>
        <v-card-text>
          <p>Здесь будет дополнительная информация о фильме.</p>
          <v-btn color="primary" @click="goBack">Назад</v-btn>
        </v-card-text>
      </v-card>
    </v-container>
  </template>
  
  <script>
  export default {
    props: ['id'],
    data() {
      return {
        movieTitle: '',
      };
    },
    created() {
      const movie = { 1: 'Интерстеллар', 2: 'Начало', 3: 'Матрица' };
      this.movieTitle = movie[this.$route.params.id];
    },
    methods: {
      goBack() {
        this.$router.push({ name: 'Home' });
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
  
  .movie-details-card {
    margin-top: 30px;
    border-radius: 10px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  }
  
  .movie-title {
    font-weight: bold;
    color: #424242;
    font-size: 1.5rem;
    padding: 10px;
  }
  
  v-btn {
    margin-top: 20px;
  }
  </style>
  