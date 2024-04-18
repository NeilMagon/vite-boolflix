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
        <h1>BOOLFIX</h1>
        <div>
            <input type="text" v-model="store.userInput" placeholder="Cerca film o serieTV">
            <button @click="$emit('searchMoviesSeries')">Cerca</button>
        </div>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as *;
    section{
        display: flex;
        justify-content: space-between;
        align-items: center;
        h1{
            color: red;
        }
        input{
            margin-right: 10px;
            padding: 5px;
        }
        button{
            padding: 5px;
            cursor: pointer;
        }
    }
</style>