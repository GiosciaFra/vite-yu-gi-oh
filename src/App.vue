<script>

import axios from 'axios';

import {store} from './store.js';

import CardList from './components/CardList.vue';

import AppNav from './components/AppNav.vue'

import CardSearch from './components/CardSearch.vue';

export default {
    data() {
        return {
            loading: true,
            cards: [],

            store,
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=600&offset=0').then(res => {

            this.store.cards = res.data.data;
            this.store.totalCards = res.data.meta.total_rows;
            this.loading = false;
        })
    },

    components: {
     CardList,
     AppNav,
     CardSearch
  },
    
    methods: {
        
    },
    
}
</script>

<template>
    
    <div v-if="loading" class="loader">
        <div id="logo-wait">
            
            <img src="/public/img/logo.png" alt="">
            
            <span>Please wait, we are loading your favorite cards!</span>
            
        </div>
    </div>
    <AppNav v-if="!loading"></AppNav>
    <CardSearch></CardSearch>
    <CardList v-if="!loading"></CardList>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/variables' as *;

#logo-wait {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    height: 100vh;

    img {
        max-width: 700px;
        padding-bottom: 50px;
    }

    span {
        font-weight: bold;
        font-size: 40px;
    }
}
</style>
