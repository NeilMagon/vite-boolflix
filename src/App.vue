<script>
    import AppHeader from './components/AppHeader.vue';
    import MainMovies from './components/MainMovies.vue';
    import axios from 'axios';
    import { store } from './store.js';
    export default {
        components: {
            AppHeader,
            MainMovies
        },
        data() {
        return {
            store
        }
    },
    methods: {
        getMoviesSeries(){
            const queryParams= {
                api_key: 'e99307154c6dfb0b4750f6603256716d',
                query: store.userInput
            };
            axios.get('https://api.themoviedb.org/3/search/movie',{
                params: queryParams
            })
            .then((response) =>{
                this.store.movies = response.data.results
            });
            axios.get('https://api.themoviedb.org/3/search/tv',{
                params: queryParams
            })
            .then((response) =>{
                this.store.series = response.data.results
            })
        }
    },
    }
</script>

<template>
    <header>
        <AppHeader @searchMoviesSeries="getMoviesSeries"></AppHeader>
    </header>
    <main>
        <MainMovies></MainMovies>
    </main>
</template>

<style scoped lang="scss">
    @use './style/generic' as *;
</style>