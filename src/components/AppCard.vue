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
    height: 200px;
    width: calc((100% - 4rem)/ 5);
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
</style>