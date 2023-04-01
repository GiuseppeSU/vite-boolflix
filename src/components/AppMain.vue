<script>
import { store } from '../store.js'
import FilmCard from './FilmCard.vue';
export default {
    name: 'AppMain',
    data() {
        return {
            store

        }
    },
    components: {
        FilmCard,
    }
}
</script>
<template>
    <div class="container">
        <FilmCard v-for="film in store.filmList" :titolo="film.title" :titoloTrue="film.original_title"
            :lingua="film.original_language" :voto="film.vote_average">
        </FilmCard>

    </div>
</template>
<style scoped></style>