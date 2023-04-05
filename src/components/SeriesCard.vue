<template>
    <div class="container mb-5 ">
        <div class="row">
            <div class="col">
                <div class="card">
                    <img :src="getImg(image)">
                    <div class="card-body text-center ms_bgColor text-light">
                        <h1 class="mb-3 fs-5">{{ titolo }}</h1>
                        <!-- <h3>{{ titoloTrue }}</h3> -->
                        <img class="image mb-2" :src="getImageUrl(`assets/${lingua}.png`)" v-if="flags.includes(lingua)" />
                        <p v-else>
                        <h3 class=" fs-6">{{ lingua }}</h3>
                        </p>
                        <p><i v-for="n in vote" class="fa-solid fa-star ms_color"></i></p>
                    </div>
                </div>

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
.ms_color {
    color: orange;
}

.image {
    height: 30px;
}

.ms_bgColor {
    background-color: rgb(131, 16, 16);
}
</style>