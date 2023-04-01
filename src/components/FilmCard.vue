<template>
    <div class="container-card">
        <div class="card">
            <div>
                <h1>{{ titolo }}</h1>
                <h3>{{ titoloTrue }}</h3>
            </div>
            <div class="container-text">
                <p class="lingua">{{ lingua }}</p>
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

    }
}
</script>


<style scoped>
.container-text {

    margin-left: 20px;
}

.lingua {
    font-size: 25px;

}
</style>