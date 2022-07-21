<template>
  <div>
    <FilmList 
        :films="films"/>
  </div>
</template>

<script>
import FilmList from "./FilmList.vue";
export default {
    props: ['films'],
    
    components: { FilmList }
}
</script>

<style>

</style>