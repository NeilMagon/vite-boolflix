<script>
    import MovieLanguage from './MovieLanguage.vue';
    import { store } from '../store.js';
    export default {
        name: 'MainMovies',
        components: {
            MovieLanguage
        },
        data() {
            return {
                store
            };
        },
    }
</script>

<template>
    <section class="container">
        <div class="col" v-for="movie in store.movies">
            <div>Name:{{ movie.title }}</div>
            <div>Original Name: {{ movie.original_title }}</div>
            <MovieLanguage></MovieLanguage>
            <div>Vote:{{ movie.vote_average }}</div>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .container{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        .col{
            width: calc(100% / 4 - 15px);
        }
    }
</style> 