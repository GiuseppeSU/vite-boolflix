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
    getFilms() {



    }

  },
  created() {


    axios.get("https://api.themoviedb.org/3/search/movie?api_key=0e52fe5f3a026a87f645a2c5c7f70271&query=avengers")
      .then(response => {
        this.store.filmList = response.data.results;

        console.log(response);
      })


  }
}




</script>

<template>
  <header>
    <AppHeader></AppHeader>
  </header>



  <main>
    <AppMain></AppMain>

  </main>
</template>

<style scoped></style>
