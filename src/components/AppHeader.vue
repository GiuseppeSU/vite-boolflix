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
        <input type="text" placeholder="Cerca il tuo Film!" v-model="store.search">
        <button @click="$emit('doSearch')">Cerca!</button>
    </div>
</template>

<style scoped>
.search-bar {
    text-align: center;
    margin-top: 30px;
}
</style>