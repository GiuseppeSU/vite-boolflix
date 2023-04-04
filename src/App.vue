<script>
import axios from 'axios'
import { store } from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
export default {
  components: {
    AppHeader,
    AppMain,

  },
  data() {
    return {
      store

    }

  },
  methods: {
    searchAll() {
      this.getFilms();
      this.getSeriestv();

    },
    getFilms() {
      let urlApi = "https://api.themoviedb.org/3/search/movie?api_key=0e52fe5f3a026a87f645a2c5c7f70271"
      if (store.search.length > 0) {
        urlApi += `&query=${store.search}`
      }
      axios.get(urlApi)
        .then(response => {
          this.store.filmList = response.data.results;
        })
    },
    getSeriestv() {
      let urlApi = "https://api.themoviedb.org/3/search/tv?api_key=0e52fe5f3a026a87f645a2c5c7f70271"
      if (store.search.length > 0) {
        urlApi += `&query=${store.search}`
      }
      axios.get(urlApi)
        .then(response => {
          this.store.serieslist = response.data.results;
        })

    }

  },
  created() {
    this.getFilms();
    this.getSeriestv();
  }
}




</script>

<template>
  <header>
    <AppHeader @doSearch="searchAll"></AppHeader>
  </header>



  <main>
    <AppMain></AppMain>

  </main>
</template>

<style scoped></style>
