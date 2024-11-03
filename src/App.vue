<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
    data() {
        return {
            store 
        };
    },
    components: {
        AppHeader,
        AppMain,
        AppFooter,
    },
    created() {
        axios.get(this.store.baseUrl)
            .then((response) => {
                this.store.Characters = response.data.results; 
                console.log(this.store.Characters);
            })
            .catch((error) => {
                console.error('Errore durante il caricamento dei dati:', error);
            });
    }
}
</script>

<template>
    <AppHeader />
    <AppMain />
    <AppFooter />
</template>

<style lang="scss">
@use "assets/scss/main" as *;
@import "assets/scss/partials/reset";
</style>
