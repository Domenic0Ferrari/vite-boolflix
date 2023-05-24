<script>
import { store } from '../store';
export default {
    data() {
        return {
            store
        }
    },
    methods: {
        // emitSearchBar() {
        //     this.$emit('performSearch');
        // },
    },
}
</script>

<template>
    <header>
        <div class="container">
            <h1>BOOLFLIX</h1>
            <div class="search">
                <input type="text" placeholder="Cerca Film o SerieTV" v-model="store.SearchBar"
                    @keyup.enter="this.$emit('performSearch')">
                <button @click="this.$emit('performSearch')">SEARCH</button>
            </div>
        </div>
    </header>
</template>

<style scoped>
.container {
    margin: 0 auto;
    padding: 1rem;
    max-width: 1000px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>