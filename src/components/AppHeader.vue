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
        <input type="text" v-model="store.userImput">
        <button @click="$emit('searchMovieSeries')">Cerca</button>
    </section>
</template>

<style scoped lang="scss"></style>