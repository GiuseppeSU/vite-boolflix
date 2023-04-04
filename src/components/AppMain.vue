<script>
import { store } from '../store.js'
import FilmCard from './FilmCard.vue';
import SeriesCard from './SeriesCard.vue';
export default {
    name: 'AppMain',
    data() {
        return {
            store

        }
    },
    components: {
        FilmCard,
        SeriesCard
    }
}
</script>
<template>
    <section>
        <h2 class="title">film</h2>
        <div class="container">
            <FilmCard v-for="film in store.filmList" :titolo="film.title" :titoloTrue="film.original_title"
                :lingua="film.original_language" :voto="film.vote_average">
            </FilmCard>

        </div>
    </section>

    <section>
        <h2 class="title">Serie TV</h2>
        <div class="container">
            <SeriesCard class="card" v-for="series in store.serieslist" :titolo="series.name"
                :titoloTrue="series.original_name" :lingua="series.original_language" :voto="series.vote_average">
            </SeriesCard>

        </div>
    </section>
</template>
<style scoped>
.title {
    font-size: 40px;
    color: red;
    margin-bottom: 50px;
}
</style>