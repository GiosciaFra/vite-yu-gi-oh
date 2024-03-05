<script>
export default {
    name: 'CardItem',
    
    props: {
        card: Object,
    }
}
</script>

<template>
    <li>
        <img :src="card.card_images[0].image_url" alt="">

        <span id="card-name">
            {{card.name}}
        </span>
        
        <br>
        
        <span id="card-type">
            {{ card.archetype }}
        </span>
    </li>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/variables' as *;


li {

    padding-bottom: 15px;
    background-color: rgba(122, 12, 4, 0.288);

    
    width: calc(100% /5 - $cardGap / 5 * 4);
    img {
        width: 100%;
    }

    #card-name {
        font-weight: 800;
        font-size: 16px;
        padding-bottom: 50px;
    }

    #card-type {
        font-weight: 600;
        font-size: 14px;
        color:rgb(0, 0, 0);
    }
}
</style>