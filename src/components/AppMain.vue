<script>
import { store } from '../store.js'
import FilmCard from './FilmCard.vue';
export default {
    name: 'AppMain',
    data() {
        return {

        }
    },
    components: {
        FilmCard,
    }
}
</script>
<template>
    <FilmCard></FilmCard>
</template>
<style scoped></style>