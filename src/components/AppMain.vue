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
        <h2>FILM</h2>
        <div class="founded">
            <AppCard v-for="movies in store.ArrMovies" :title="movies.title" :original_language="movies.original_language"
                :vote_average="movies.vote_average" :original_title="movies.original_title" />
        </div>
        <h2>SERIE TV</h2>
        <div class="founded">
            <AppCard v-for="movies in store.ArrTvSeries" :title="movies.title" :original_language="movies.original_language"
                :vote_average="movies.vote_average" :original_title="movies.original_title" />
        </div>

    </div>
</template>

<style scoped>
.container {
    max-width: 1000px;
    padding: 1rem;
    margin: 0 auto;
}

.founded {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.series {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}
</style>