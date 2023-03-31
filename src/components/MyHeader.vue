<script>
import { store } from '../store.js';
export default {
    name: 'MyHeader',
    data() {
        return {

        }
    }

}
</script>

<template>
    <div class="search-bar">
        <input type="text" placeholder="Cerca il tuo Film!">
        <button>Cerca!</button>
    </div>
</template>

<style scoped>
.search-bar {
    text-align: center;
    margin-top: 30px;
}
</style>