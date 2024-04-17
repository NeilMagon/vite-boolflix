<script>
    import { store } from '../store.js';
    export default {
        name: 'AppHeader',
        data() {
            return {
                store
            };
        },
    }
</script>

<template>
    <section>
        <input type="text" v-model="store.userInput">
        <button @click="$emit('searchMoviesSeries')">Cerca</button>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
</style>