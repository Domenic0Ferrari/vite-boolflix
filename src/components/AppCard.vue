<script>
export default {
    props: {
        title: String,
        original_language: String,
        original_title: String,
        vote_average: Number,
    },
};
</script>

<template>
    <div class="card">
        <div>
            {{ title }}
        </div>
        <div>
            {{ original_language }}
        </div>
        <div>
            {{ original_title }}
        </div>
        <div>
            {{ vote_average }}
        </div>
    </div>
</template>


<style scoped>
.card {
    height: 100px;
    border: 1px solid black;
}
</style>