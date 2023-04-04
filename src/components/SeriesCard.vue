<template>
    <div class="container-card">
        <div class="card">
            <div>
                <img :src="getImg(image)">
                <h1>{{ titolo }}</h1>
                <h3>{{ titoloTrue }}</h3>
            </div>
            <div class="container-text">
                <img class="image" :src="getImageUrl(`assets/${lingua}.png`)" v-if="flags.includes(lingua)" />
                <p v-else>
                <h3 class="lingua">{{ lingua }}</h3>
                </p>
                <p>{{ vote }}</p>
                <i class=" fa-solid fa-star"></i>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SeriesCard',

    props: {
        image: String,
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
        },
        getImg(image) {
            let urlImg = "https://image.tmdb.org/t/p/w342/" + image
            return urlImg
        }
    },
    computed: {
        vote() {
            return Math.ceil(this.voto * 5 / 10)

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

.container-card {
    margin-bottom: 50px;
}
</style>