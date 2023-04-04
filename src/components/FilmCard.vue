<template>
    <div class="container-card">
        <div class="card">
            <div>
                <h1>{{ titolo }}</h1>
                <h3>{{ titoloTrue }}</h3>
            </div>
            <div class="container-text">
                <img class="image" :src="getImageUrl(`assets/${lingua}.png`)" v-if="flags.includes(lingua)" />
                <P v-else>
                <h3 class="lingua">{{ lingua }}</h3>
                </P>
                <p>{{ voto }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FilmCard',

    props: {
        titolo: String,
        titoloTrue: String,
        lingua: String,
        voto: Number

    },
    data() {
        return {
            flags: ["en", "it"]

        }
    },
    methods: {
        getImageUrl(path) {
            return new URL(path, import.meta.url).href
        }
    }
}
</script>


<style scoped>
.lingua {
    font-size: 25px;

}

.image {
    height: 50px;
}
</style>