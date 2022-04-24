<template>
  <div id="app">
      <Header @newSearch="updateMovieSearch"/>

      <Main :movies='movies'/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },

  data: function(){
      return {
          movies: [],
          // apiURL: 'https://api.themoviedb.org/3/search/movie?api_key=77f91f2f71f3f870afab1c37d553c29a&query=',
          movieSearch: '', 
      }
    },

  methods : {
      updateMovieSearch(stringToSearch){
        this.movieSearch = stringToSearch;
        console.warn(this.movieSearch);
        this.getApiMovies;
      },

      getApiMovies(){
            axios
            .get('https://api.themoviedb.org/3/search/movie?api_key=77f91f2f71f3f870afab1c37d553c29a&query=`${movieSearch}`')
            .then((response) => {
                this.movies = response.data.results;
                console.table(this.movies);
            })
            .catch((error) => {
                console.log(error)
            })
        }
  }
}
</script>

<style lang="scss">
@import './assets/style/style.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>

// ! Chiave API
//! 77f91f2f71f3f870afab1c37d553c29a