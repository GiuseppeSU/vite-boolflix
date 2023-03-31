<script>
import axios from 'axios'
import { store } from './store.js'

import MyHeader from './components/MyHeader.vue'


export default {
  components: {
    MyHeader
  },
  data() {
    return {
      store

    }

  },
  methods: {
    getFilms() {
      let urlApiFilm = "https://api.themoviedb.org/3/search/movie?api_key=0e52fe5f3a026a87f645a2c5c7f70271&query=avengers";

      axios.get(urlApiFilm)
        .then(response => {
          this.store.filmList = response.data.results;
        })

    },




  }
}

</script>

<template>
  <header>
    <MyHeader></MyHeader>
  </header>
  <main></main>
  <footer></footer>
</template>

<style scoped></style>
