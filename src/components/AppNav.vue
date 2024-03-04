<script>
export default {
    name: 'AppNav',
}
</script>

<template>

    <nav>
        <img id="logo" src="/public/img/logo.png" alt="">
    </nav>

        
    
</template>

<style lang="scss">
@use '../styles/general.scss' as *;
@use '../styles/variables' as *;


nav {
    display: flex;
    padding: 30px 0;
    justify-content: center;

    #logo {
        max-width: 350px;
    }
}
</style>