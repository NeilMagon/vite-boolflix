<script>
    import { store } from '../store.js';
    export default {
        name: 'MainMovies',
        data() {
            return {
                store
            };
        },
    }
</script>

<template>
    <section>
        <div v-for="movie in store.movies">
            <div>Name:{{ movie.title }}</div>
            <div>Original Name: {{ movie.original_title }}</div>
            <div>Language:{{ movie.original_language }}</div>
            <div>Vote:{{ movie.movie.vote_average }}</div>
        </div>
    </section>
</template>

<style scoped lang="scss"></style> 