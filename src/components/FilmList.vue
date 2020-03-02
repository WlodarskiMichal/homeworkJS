<template lang="html">
  <div >
    <!-- <button class="button" type="button" name="sortby">Sort by RT score</button> -->
    <ul>
      <li class="flex-container" v-for="(film, index) in films" :film="film" :key="index">
        <h2>{{film.title}}</h2><br>
        <p>{{film.description}}</p>
        <p class="tomatoes"> Rotten tomatoes score: {{film.rt_score}} <img class="image" src="../../public/rotten.png" alt=""></p>

      </li>
      <film-list-item>Find more</film-list-item>

    </ul>

  </div>
</template>

<script>

import FilmListItem from './FilmListItem.vue'

export default {
  name:'film-list',

  data(){
    return{
      film:[]
    }
  },
  props:['films'],
  components:{
    'film-list-item':FilmListItem
  }
}
</script>

<style lang="css" scoped>
.tomatoes{
  position: relative; bottom:0;
}
.image{
  height: 12px;
  width: 12px;
}
.flex-container {
  display:  inline-table;
  /* justify-content: flex-start; */
  justify-content: flex-start;
  flex-flow: row wrap;
  /* flex-wrap: wrap;
  flex-flow: flex-wrap || flex-direction; */
  /* background-color: DodgerBlue; */
  width: 300px;
  height: auto;
  margin: 10px;
  /* margin: 10px; */
  text-align: center;
  /* line-height: 75px; */
  /* font-size: 30px; */

  /* flex-direction: column; */
  align-self: auto;
}

.flex-container {
  background-color: #f1f1f1;
  border-radius: 25px;
}
.button{
  align-content: center;
}
</style>
