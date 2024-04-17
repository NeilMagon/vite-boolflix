<script>
    import AppHeader from './components/AppHeader.vue';
    import MainMovies from './components/MainMovies.vue';
    import MainSeries from './components/MainSeries.vue';
    export default {
        components: {
            AppHeader,
            MainMovies,
            MainSeries
        }
    }
</script>

<template>
    <header>
        <AppHeader></AppHeader>
    </header>
    <main>
        <MainMovies></MainMovies>
        <MainSeries></MainSeries>
    </main>
</template>

<style scoped lang="scss">
    @use './style/generic' as *;
</style>