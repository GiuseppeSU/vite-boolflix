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
<template >
    <section v-if="store.filmList.length > 0">
        <h2 class="text-center text-danger fs-1 mb-4">Film</h2>
        <div class="container">
            <div class="row">
                <div class="col mb-5" v-for="film in store.filmList">
                    <FilmCard :image="film.poster_path" :titolo="film.title" :titoloTrue="film.original_title"
                        :lingua="film.original_language" :voto="film.vote_average" :key="film.id">
                    </FilmCard>
                </div>
            </div>
        </div>
    </section>

    <section v-if="store.serieslist.length > 0">
        <h2 class="text-danger fs-1 mb-4 text-center">Serie TV</h2>
        <div class="container">
            <div class="row ">
                <div class="col mb-5" v-for="series in store.serieslist">
                    <SeriesCard :image="series.poster_path" :titolo="series.name" :titoloTrue="series.original_name"
                        :lingua="series.original_language" :voto="series.vote_average" :key="series.id">
                    </SeriesCard>

                </div>
            </div>

        </div>
    </section>
    <h2 v-if="store.filmList.length == 0 && store.serieslist.length == 0">Nessun elemento trovato</h2>
</template>
<style scoped></style>