<template>
  <div id="app">
      <Header @newSearch="updateMovieSearch"/>

      <Main :moviesAndSeries='moviesAndSeries'/>
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
          series: [],
          moviesAndSeries: [],
          apiURL: 'https://api.themoviedb.org/3/search/',
          apiKey: '?api_key=77f91f2f71f3f870afab1c37d553c29a&query=',
          movieSearch: '' 
      }
    },

  methods : {
      updateMovieSearch(stringToSearch){
        this.movieSearch = stringToSearch;
        // console.warn(this.movieSearch);
        this.getApiMovies();
        this.getApiSeries();
      },
      
      // Chiamata API x le i film
      getApiMovies(){
            axios
            .get(this.apiURL + 'movie' + this.apiKey + this.movieSearch)
            .then((response) => {
                this.movies = response.data.results;
                this.moviesAndSeries = [...this.movies, this.series];
                console.table(this.moviesAndSeries);
            })
            .catch((error) => {
                console.log(error)
            })
        },
      
      // Chiamata API x le serie TV
      getApiSeries(){
            axios
            .get(this.apiURL + 'tv' + this.apiKey + this.movieSearch)
            .then((response) => {
                this.series = response.data.results;
                this.moviesAndSeries = [...this.movies, this.series];
                console.table(this.moviesAndSeries);
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
  background-color: rgb(88, 75, 75);
}
</style>

// ! Chiave API
//! 77f91f2f71f3f870afab1c37d553c29a