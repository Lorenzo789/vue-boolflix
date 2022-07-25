<template>
  <div class="container">
    <div>
        <h1>BOOLFIX</h1>
    </div>
    <div>
        <input @keyup.enter="$emit('search', inputSearch)" type="text" placeholder="Search"
            v-model="inputSearch">

        <button @click="$emit('search', inputSearch)">
            Cerca
        </button>
    </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            inputSearch: '',
        }
    },
}
</script>

<style lang="scss" scoped>
@import'../styles/variables.scss';

    .container{
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 10px;
        background-color: $blackBg;

        h1{
            color: $red;
        }

        input{
            margin-right: 10px;
            padding: 10px;
        }

        button{
            background-color: $red;
            border-color: $red;
            padding: 10px;
            color: white;
            font-weight: bold;
            text-transform: uppercase;
        }
    }
</style>