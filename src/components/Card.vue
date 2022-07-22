<template>
  <div>
    <div class="card">
      <img :src="`${baseUrlDimension}${imageUrl}`" alt="">
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

      if (language == 'en') {
        return 'gb';
      } else if (language == 'ja') {
        return 'jp';
      } else {
        return 'not-present';
      }
    },
    flagSwitch(language){
      switch (language) {
        case 'it':
          console.log('italiano');
        break;
        case 'en':
          console.log('inglese');
        break;
        case 'fr':
          console.log('francese');
        break;
        case 'jp':
          console.log('giapponese');
        break
        case 'ru':
          console.log('russa');
        break
        case 'de':
          console.log('tedesca');
        break
        default:
          console.log('non registrata');
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