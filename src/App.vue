<script>
    import AppHeader from './components/AppHeader.vue';
    import MainMovies from './components/MainMovies.vue';
    import MainSeries from './components/MainSeries.vue';
    import axios from 'axios';
    import { store } from './store.js';
    export default {
        components: {
            AppHeader,
            MainMovies,
            MainSeries
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
        <MainSeries></MainSeries>
    </main>
</template>

<style scoped lang="scss">
    @use './style/generic' as *;
</style>