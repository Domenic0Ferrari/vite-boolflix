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
    <main>
        <div class="container">
            <h2>FILM</h2>
            <div class="founded">
                <AppCard v-for="movies in store.ArrMovies" :title="movies.title"
                    :original_language="movies.original_language" :vote_average="movies.vote_average"
                    :original_title="movies.original_title" :poster_path="movies.poster_path" />
            </div>
            <h2>SERIE TV</h2>
            <div class="founded">
                <AppCard v-for="series in store.ArrTvSeries" :title="series.name"
                    :original_language="series.original_language" :vote_average="series.vote_average"
                    :original_title="series.original_name" :poster_path="series.poster_path" />
            </div>
        </div>
    </main>
</template>

<style scoped>
main {
    background-color: #434343;
}

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