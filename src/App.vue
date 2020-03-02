<template>
  <div id="app">
    <h1 class = "header" > Studio Ghibli </h1>
    <button v-on:click="sort">Sort by RT score</button>
    <film-list :films="films"></film-list>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue'

export default {
  name:'app',
  data(){
    return{
      films:[]
    }
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(response => response.json())
    .then(data => this.films = data)
    // console.log(this.films);
  },
  computed: {
    favourites: function() {
      return this.films.filter(film => film.isFavourite);
    }
  },
  components: {
    "film-list":FilmList
  },
  methods:{
  sort: function() {
      return this.films.rt_score.sort((a, b) => {
        return a[property] < b[property] ? -1 : 1;
      });}
  }}

</script>

<style>
.header{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  font-size: 5em;
}
#app{
  background-image: url('../public/back.jpg');
  background-repeat:no-repeat;
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}
</style>
