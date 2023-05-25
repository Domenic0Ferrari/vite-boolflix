<script>
// import flag
import CountryFlag from 'vue-country-flag-next'
export default {
    data() {
        return {
        }
    },
    components: {
        CountryFlag
    },
    methods: {
        convertVote(vote) {
            const convertedVote = Math.ceil(vote / 2);
            return convertedVote;
        },
    },
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
            <span>TITOLO:</span>
            {{ title }}
        </div>
        <div>
            <span>TITOLO ORIGINALE:</span>
            {{ original_title }}
        </div>
        <div>
            <span>LINGUA ORIGINALE:</span>
            <country-flag v-if="original_language === 'en'" country='gb' size='normal' />
            <country-flag v-else-if="original_language === 'ko'" country='kr' size='normal' />
            <country-flag v-else-if="original_language === 'ja'" country='jp' size='normal' />
            <country-flag v-else-if="original_language === 'zh'" country='cn' size='normal' />
            <country-flag v-else-if="original_language === 'hi'" country='in' size='normal' />
            <country-flag v-else :country='original_language' size='normal' />
        </div>
        <div>
            <span>VOTO:</span>
            {{ convertVote(vote_average) }}
        </div>
    </div>
</template>


<style scoped>
.card {
    height: 300px;
    width: calc((100% - 2rem)/ 3);
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
</style>