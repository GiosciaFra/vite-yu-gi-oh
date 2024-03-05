<script>

import CardItem from './CardItem.vue';


import {store} from '../store.js';


export default {
    name: 'CardList',

    components: {
        CardItem
    },

    data() {
        return{
            store,
        }
    }
}


</script>

<template>

<div class="container">


    <div class="showed-cards">
        <div id="result">
            We found {{ store.totalCards}} cards for "{{ store.selectItem }}" Archetype
        </div>
    </div>
    <ul>
        <CardItem
        v-for="card in store.cards"
        :card="card">
           
        
        </CardItem>
    </ul>
    </div>
</template>


<style lang="scss" scoped>
@use '../styles/general' as *;
@use '../styles/variables' as *;

.container {
    background-color: rgb(255, 134, 134);

    .showed-cards {

        
        #result {
            display: block;
            padding: 24px;
            background-color: rgba(53, 4, 0, 0.288);
            margin-bottom: 40px;
            text-transform: uppercase;
            font-weight: 700;
        }
    } 
    ul {
        display: flex;
        gap: $cardGap;
        flex-flow: wrap;
        list-style: none;
        text-align: center;
    }
}

</style>