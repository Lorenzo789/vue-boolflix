<template>
  <div class="card-parent">
    <ul class="card"         
        @mouseover="hover = true"
        @mouseleave="hover = false" 
        :style="{'background-image': `url(${baseUrlDimension}${imageUrl})`}">

      <transition name="fade">
        <div class="hover-card" v-if="hover">
          <h4> <strong>Titolo:</strong>  
            {{ title }}
          </h4>

          <h4> <strong>Titolo originale:</strong>  
            {{ originalTitle }}
          </h4>

          <span :class="`fi-${returnStringFlag(originalLanguage)} fi flag`"></span>

          <span> <strong>Voto:</strong> 
            <i class="fa-solid fa-star" v-for="(star, index) in changeVoteIntoStars(vote)" :key="index"></i>
          </span>

          <p>{{ overview }}</p>
        </div>
      </transition>
    </ul>
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
    overview: String,
  },
  data: function(){
    return{
      baseUrlDimension: 'https://image.tmdb.org/t/p/w342/',
      hover: false,
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
        case 'es':
          return 'es';
        default:
          return 'not-present';
      }
    },
    changeVoteIntoStars(vote){
      let newVote = Math.ceil((vote * 5) / 10);
      return newVote;
    },
  },
}
</script>

<style lang="scss" scoped>
@import'../styles/variables.scss';

  .card-parent{
    width: calc(100% / 4 - 20px);
    height: 500px;
    margin-bottom: 20px;
    margin-right: 20px;
    .hover-card{
      overflow: auto;
      height: 100%;
      padding: 20px;
      background-color: black;
      color: white;
      text-align: start;
      h4{
        margin-bottom: 10px;
      }
      span{
        margin-bottom: 10px;
      }
      p{
        margin: 10px 0px;
        text-align: center;
      }
    }
    .card{
      height: 100%;
      list-style: none;
      }
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
      span>i{
        color: yellow;
      }
      .fade-enter-active, .fade-leave-active {
      transition: opacity .7s;
      }
      .fade-enter, .fade-leave-to{
        opacity: 0;
      }
    }
</style>