<script>
    import { store } from '../store.js';
    export default {
        name: 'CardMovies',
        props: {
            cardInfo: Object
        },
        data() {
            return {
                flags: [
                    {lang: 'it'},
                    {lang: 'en'},
                    {lang: 'fr'},
                    {lang: 'de'},
                    {lang: 'es'},
                ],
            };
        },
        methods: {
            getImageUrl(name) {
                return new URL(`../assets/img/${name}-flag.png`, import.meta.url).href
            }
        }
    }
</script>

<template>
    <div class="col">
        <div>Name:{{ cardInfo.title }}</div>
        <div>Original Name: {{ cardInfo.original_title }}</div>
        <div class="img-container" v-if="cardInfo.original_language === flags[0].lang">
            Language: 
            <div class="flag-container">
                <img :src="getImageUrl(flags[0].lang)" :alt="cardInfo.original_language">
            </div>
        </div>
        <div class="img-container" v-else-if="cardInfo.original_language === flags[1].lang">
            Language: 
            <div class="flag-container">
                <img :src="getImageUrl(flags[1].lang)" :alt="cardInfo.original_language">
            </div>
        </div>
        <div class="img-container" v-else-if="cardInfo.original_language === flags[2].lang">
            Language: 
            <div class="flag-container">
                <img :src="getImageUrl(flags[2].lang)" :alt="cardInfo.original_language">
            </div>
        </div>
        <div class="img-container" v-else-if="cardInfo.original_language === flags[3].lang">
            Language: 
            <div class="flag-container">
                <img :src="getImageUrl(flags[3].lang)" :alt="cardInfo.original_language">
            </div>
        </div>
        <div class="img-container" v-else-if="cardInfo.original_language === flags[4].lang">
            Language: 
            <div class="flag-container">
                <img :src="getImageUrl(flags[4].lang)" :alt="cardInfo.original_language">
            </div>
        </div>
        <div>Vote:{{ cardInfo.vote_average }}</div>
    </div>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .col{
            width: calc(100% / 4 - 15px);
            .img-container{
                width: 200px;
                display: flex;
                .flag-container{
                    width: 30px;
                }
            }
            img{
                width: 100%;
            }
        }
   

</style>