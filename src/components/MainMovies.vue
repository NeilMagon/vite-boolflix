<script>
    import CardMovies from './CardMovies.vue';
    import { store } from '../store.js';
    export default {
        name: 'MainMovies',
        components: {
            CardMovies
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
        <h1>Movies</h1>
        <div class="d-flex">
            <CardMovies v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></CardMovies>
        </div>
    </section>
    <section class="container">
        <h1>Series</h1>
        <div class="d-flex">
            <CardMovies v-for="series in store.series" :key="series.id" :cardInfo="series"></CardMovies>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .d-flex{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
    }
</style> 
