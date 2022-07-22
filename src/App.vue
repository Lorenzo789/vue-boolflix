<template>
  <div id="app">
    <Header @search="textToSearch"/>
    <Main
      :films="searchedFilm"
      :tvShows="searchedTvSohws"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function(){
    return{
      searchedFilm: [],
      searchedTvSohws: [],
      apiKey: '5d52abd6795445439ccc206e6fdec146',
    }
  },
  methods: {
    textToSearch(inputSearch){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&language=it-IT&query=${inputSearch}&include_adult=true`)
      .then((result) => {
        console.log(inputSearch + 'film');
        this.searchedFilm = result.data.results;
        console.log(this.searchedFilm);
      })
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&language=it-IT&query=${inputSearch}&include_adult=true`)
      .then((resultShow) => {
        console.log(inputSearch + 'serie');
        this.searchedTvSohws = resultShow.data.results;
        console.log(this.searchedTvSohws);
      })
    },
  }
}
</script>

<style lang="scss" scoped>
@import'../node_modules/flag-icons/css/flag-icons.css';

</style>
