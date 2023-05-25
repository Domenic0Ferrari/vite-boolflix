<script>
import { store } from '../store';
import AppCard from './AppCard.vue';
export default {
    data() {
        return {
            store,
        };
    },
    components: {
        AppCard,
    },
}
</script>

<template>
    <div class="container">
        <AppCard v-for="movies in store.ArrMovies" :title="movies.title" :original_language="movies.original_language"
            :vote_average="movies.vote_average" :original_title="movies.original_title" />
    </div>
</template>

<style scoped>
.container {
    max-width: 1000px;
    padding: 1rem;
    margin: 0 auto;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}
</style>