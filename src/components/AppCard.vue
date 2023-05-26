<script>
// import flag
import { far } from "@fortawesome/free-regular-svg-icons";
import { fas } from "@fortawesome/free-solid-svg-icons";
import CountryFlag from 'vue-country-flag-next'
export default {
    data() {
        return {
        }
    },
    components: {
        CountryFlag,
        far,
        fas
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
        poster_path: String,
    },
};
</script>

<template>
    <div class="card">
        <div class="container_card">
            <img class="img_card" v-if="poster_path" :src="'https://image.tmdb.org/t/p/w342' + poster_path" alt="#">
            <img class="img_card" v-else src="../assets/fallback-image.png" alt="#">
        </div>
        <div class="container_information">
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
                <div class="star">
                    <div v-for="index in 5" :key="index">
                        <font-awesome-icon v-if="index < convertVote(vote_average)" icon="fa-star" />
                        <font-awesome-icon v-else :icon="['far', 'star']" />
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>
.card {
    width: calc((100% - 2rem)/ 3);
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.container_card {
    max-width: 100%;
    height: 100%;
    display: block;
}

/* .container_card:hover {
    display: none;
} */

.img_card {
    max-width: 100%;
    height: 100%;
}

.star {
    display: flex;
    justify-content: space-around;
}
</style>