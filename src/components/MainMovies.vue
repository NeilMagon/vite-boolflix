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
        <CardMovies v-for="movie in store.movies" :key="movie.id" :cardInfo="movie"></CardMovies>
    </section>
    <section class="container">
        <CardMovies v-for="series in store.series" :key="series.id" :cardInfo="series"></CardMovies>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .container{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
    }
</style> 
