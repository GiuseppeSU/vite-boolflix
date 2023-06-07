<script>
import { store } from '../store.js';
export default {
    name: 'AppHeader',
    data() {
        return {
            store,


        }
    }

}
</script>

<template>
    <div class="search-bar">
        <h1>Boolflix</h1>
        <div class="input">
            <input type="text" placeholder="Cerca il tuo Film!" v-model="store.search">
            <button class="btn btn-danger ms-2 mb-1" @click="$emit('doSearch')">Cerca!</button>
        </div>
    </div>
</template>

<style scoped>
.search-bar {
    display: flex;
    background-color: black;
    align-items: center;
    justify-content: space-between;
    padding: 20px;
}

h1 {
    margin-left: 20px;
    font-size: 40px;
    color: red;
}
</style>