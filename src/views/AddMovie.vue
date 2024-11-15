<template>
    <v-container>
      <h1 class="page-title">Добавить фильм</h1>
      <v-form @submit.prevent="addMovie">
        <v-text-field
          label="Введите название фильма"
          v-model="newMovie"
          outlined
          color="primary"
          class="input-field"
        />
        <v-btn type="submit" color="primary" class="submit-btn">Добавить фильм</v-btn>
      </v-form>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'AddMovie',
    data() {
      return {
        newMovie: '',
      };
    },
    methods: {
      addMovie() {
        if (this.newMovie.trim()) {
          const movie = {
            id: Date.now(),
            title: this.newMovie,
          };
          this.$store.dispatch('addMovie', movie);
          this.$router.push({ name: 'Home' });
        }
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
  
  .input-field {
    margin-bottom: 20px;
  }
  
  .submit-btn {
    display: block;
    margin: 20px auto;
    padding: 10px 20px;
    font-size: 1.2rem;
    width: 100%;
  }
  </style>
  