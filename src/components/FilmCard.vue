<template>
    <div class="container mb-5">
        <div class="row">
            <div class="col">
                <div class="flip-card">
                    <div class="flip-card-inner">
                        <div class="flip-card-front">
                            <img :src="getImg(image)">
                        </div>
                        <div class="flip-card-back">
                            <h1 class="fs-5 mb-3">{{ titolo }}</h1>
                            <h3 class="fs-5">{{ titoloTrue }}</h3>
                            <img class="image mb-2" :src="getImageUrl(`assets/${lingua}.png`)"
                                v-if="flags.includes(lingua)" />
                            <p v-else>
                            <h3 class=" fs-6">{{ lingua }}</h3>
                            </p>
                            <p><i v-for="n in vote" class="fa-solid fa-star mt-3 ms_color"></i></p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FilmCard',

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
        },


    },
    computed: {
        vote() {
            return Math.ceil(this.voto * 5 / 10)

        },


    }
}
</script>


<style scoped>
.image {
    height: 30px;
}

.ms_color {
    color: orange;
}

.ms_bgColor {
    background-color: rgb(131, 16, 16);
}

.flip-card {
    background-color: transparent;
    width: 300px;
    height: 500px;
    perspective: 1000px;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
}

.flip-card-front {
    background-color: #bbb;
    color: black;
}

.flip-card-back {
    background-color: #2980b9;
    color: white;
    transform: rotateY(180deg);
}
</style>