<script>

import axios from 'axios';
export default {
    data() {
        return {
            cards: [],
        }
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {

            this.cards = res.data.data
        })
    },

    mounted() {
        
    },
    
    components: {
        
    },
    
    methods: {
        
    },
    
}
</script>

<template>
    <ul>
        <li v-for="currentCard in cards">
    {{ currentCard.name }}
        </li>
    </ul>
</template>

<style lang="scss"></style>
