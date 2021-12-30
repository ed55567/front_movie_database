<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>{{ message }}</h1>
    <h2>Search for a film</h2>
    <p>Film Title:<input type="text" v-model="movie"></p>

    <div v-for="film in films">
      {{ film.title }}
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios';

export default {
  data: function() {
    return {
      message: "Welcome To Movie Database",
      movie:"enter film title here",
      films: [] 
    };
  },
  created: function() {},
   methods: {
     filmsIndex: function() {
       console.log('films index...');
       axios.get('/api/films').then(response =>{
         console.log(response.data);
      });
     }
   }
};
</script>
