<template>
  <div>
    <FilmList 
        :films="films"/>

    <TvShowList 
        :tvShows="tvShows"/>
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

</style>