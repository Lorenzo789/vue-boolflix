<template>
  <div>
    <div class="card" :style="{'background-image': `url(${baseUrlDimension}${imageUrl})`}">
      <h2>{{ title }}</h2>
      <h4>{{ originalTitle }}</h4>
      <span :class="`fi-${returnStringFlag(originalLanguage)} fi flag`"></span>
      <span>Voto: {{ vote }}</span>

    </div>
  </div>
</template>

<script>
export default {
  props: {
      imageUrl: String,
      title: String,
      originalTitle: String,
      originalLanguage: String,
      vote: Number,
  },
  data: function(){
    return{
      baseUrlDimension: 'https://image.tmdb.org/t/p/w342/',
    }
  },
  methods: {
    returnStringFlag(originalLanguage){
      const language = String(originalLanguage);

      switch (language) {
        case 'it':
          return 'it';
        break;
        case 'en':
          return 'gb';
        break;
        case 'fr':
          return 'fr';
        break;
        case 'ja':
          return 'jp';
        break
        case 'ru':
          return 'ru';
        break
        case 'de':
          return 'de';
        break
        default:
          return 'not-present';
      }
    },
  }
}
</script>

<style lang="scss" scoped>
  .card{
    
    .flag{
      display: block;
      width: 20px;
      height: 20px;
    }
    .fi-not-present{
      background-image: url('https://thumbs.dreamstime.com/b/no-image-available-icon-photo-camera-flat-vector-illustration-132483141.jpg');
      display: block;
      width: 20px;
      height: 20px;
    }
  }
</style>