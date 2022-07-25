<template>
  <div>
    <!-- FARE UNA FUNZIONE -->
    <div v-if="films.length == 0 && tvShows.length == 0">
      <h1 class="research-not-found">Not Found</h1>
    </div>
    <div v-else>
      <div class="films-container">
        <FilmList 
            :films="films"
        />
      </div>
  
      <div class="series-container">
        <TvShowList 
            :tvShows="tvShows"
        />
      </div>
    </div>
  </div>
</template>

<script>
import FilmList from "./FilmList.vue";
import TvShowList from "./TvShowList.vue";
export default {
    props: ['films', 'tvShows'],
    
    components: { FilmList, TvShowList },
}
</script>

<style lang="scss" scoped>
@import'../styles/variables.scss';

  div{
    background-color: #252525;
    padding: 10px;
  }
  .research-not-found{
    text-align: center;
    font-weight: bold;
    color: white;
    font-size: 50px;
  }

</style>