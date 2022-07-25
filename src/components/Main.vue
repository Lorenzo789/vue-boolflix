<template>
  <div>
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
</template>

<script>
import FilmList from "./FilmList.vue";
import TvShowList from "./TvShowList.vue";
export default {
    props: ['films', 'tvShows'],
    
    components: { FilmList, TvShowList }
}
</script>

<style lang="scss" scoped>
@import'../styles/variables.scss';

  div{
    background-color: #252525;
    padding: 10px;
  }

</style>