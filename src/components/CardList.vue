<script>

import CardItem from './CardItem.vue';

import {store} from '../store.js';

export default {
    name: 'CardList',

    components: {
        CardItem,
    },

    data() {
        return{
            store,
        }
    }
}


</script>

<template>

        <ul>
            <li v-for="card in store.cards">
            {{ card.name }}
            </li>
        </ul>
    
</template>


<style lang="scss">


</style>