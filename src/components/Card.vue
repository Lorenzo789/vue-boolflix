<template>
  <div>
    <div class="card">

      <h2>{{ title }}</h2>
      <h4>{{ originalTitle }}</h4>
      <span :class="`fi-${returnStringFlag(originalLanguage)} fi flag no-flag`">{{ originalLanguage }}</span>
      <span>Voto: {{ vote }}</span>

    </div>
  </div>
</template>

<script>
export default {
  props: {
      title: String,
      originalTitle: String,
      originalLanguage: String,
      vote: Number,
  },
  methods: {
    returnStringFlag(originalLanguage){
      const language = String(originalLanguage);

      if (language == 'en') {
        return 'gb';
      } else if (language == 'ja') {
        return 'jp';
      } else {
        console.log('non registrata');
      }

      return language;
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
  .flag{
    display: block;
    width: 20px;
    height: 20px;
  }
  .no-flag{
    text-transform: uppercase;
  }
</style>