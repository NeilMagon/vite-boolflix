<script>
    import { store } from '../store.js';
    export default {
        name: 'CardMovies',
        props: {
            cardInfo: Object
        },
        data() {
            return {
                store
            };
        },
    }
</script>

<template>
    <div class="col">
        <div>Name:{{ cardInfo.title }}</div>
        <div>Original Name: {{ cardInfo.original_title }}</div>
        <div>Language: {{ cardInfo.original_language }}</div>
        <div>Vote:{{ cardInfo.vote_average }}</div>
    </div>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    .col{
            width: calc(100% / 4 - 15px);
        }
</style>