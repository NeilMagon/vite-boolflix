<script>
    export default {
        name: 'CardMovies',
        props: {
            cardInfo: Object
        },
        data() {
            return {
                flags: [
                    'it',
                    'en',
                    'fr',
                    'de',
                    'es'
                ],
            };
        },
        methods: {
            getImageUrl() {
                let flagLanguage = this.cardInfo.original_language;
                return new URL(`../assets/img/${flagLanguage}-flag.png`, import.meta.url).href
            }
        }
    }
</script>

<template>
    <div class="col">
        <div class="img-container">
            <img v-if="cardInfo.poster_path === null" src="https://png.pngtree.com/thumb_back/fw800/background/20210207/pngtree-simple-gray-solid-color-background-image_557027.jpg" alt="">
            <img v-else :src="'https://image.tmdb.org/t/p/w342/' + cardInfo.poster_path" alt="">
        </div>
        <div class="position">
            <div>Name:{{ cardInfo.title || cardInfo.name }}</div>
            <div>Original Name: {{ cardInfo.original_title || cardInfo.original_name }}</div>
            <div class="language-container">
                Language: 
                <div class="flag-container">
                    <img v-if="flags.includes(cardInfo.original_language)" :src="getImageUrl()" :alt="cardInfo.original_language">
                    <div v-else>{{ cardInfo.original_language }}</div>
                </div>
            </div>
            <div>Vote:{{ cardInfo.vote_average }}</div>
            <div>Overview: {{ cardInfo.overview }}</div>
            <!-- <i class="fa-solid fa-star"></i> -->
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .col{
        width: calc(100% / 4 - 15px);
        position: relative;
        .img-container{
            width: 270px;
            height: 400px;
            overflow: hidden;
            border-radius: 10px;
            border: 1px solid white;
        }
        .language-container{
            display: flex;
            .flag-container{
                width: 30px;
            }
        }
        img{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .position{
            display: none;
            padding: 5px;
            position: absolute;
            top: 0;
            left: 0;
        }
    }
    .col:hover .position{
        display: block;
    }
    .col:hover .img-container{
        opacity: 0.1;
        transition: opacity 1s;
        transform: scale(1.1);
    }
</style>