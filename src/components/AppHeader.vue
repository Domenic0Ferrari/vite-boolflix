<script>
export default {

}
</script>

<template>
    <header>
        <div class="container">
            <h1>BOOLFLIX</h1>
            <div class="search">
                <input type="text" placeholder="Cerca Film o SerieTV" v-model="SearchBar" @keyup.enter="emitSearchBar">
                <button @click="emitSearchBar">SEARCH</button>
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