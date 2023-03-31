<script>
import axios from 'axios'
import { store } from './store.js'

import MyHeader from './components/MyHeader.vue'
import MyHeader from './components/MyHeader.vue'

export default {
  components: {
    MyHeader
  },
  data() {
    return {
      store

    }

  }, methods: {

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
