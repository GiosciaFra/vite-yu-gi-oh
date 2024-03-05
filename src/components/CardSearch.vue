<script>

import { store } from '../store';

export default {
    name: 'CardSearch',
}
</script>

<template>

<div class="dropdown">
  <button class="dropdown-btn">Select Archetype</button>
  <div class="dropdown-content">
    <a href="#">Opzione 1</a>
    <a href="#">Opzione 2</a>
    <a href="#">Opzione 3</a>
  </div>
</div>


</template>

<style lang="scss">

@use '../styles/general' as *;
@use '../styles/variables' as *;



.dropdown {
  position: relative;
  display: inline-block;

  
  &-btn {
    background-color: #ffffff;
    color: #ff5858;
    padding: 10px;
    border: none;
    cursor: pointer;
  }

  &-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.8);
    z-index: 1;

    a {
      color: black;
      padding: 12px 16px;
      text-decoration: none;
      display: block;

      &:hover {
        background-color: #ddd;
        
      }
    }
  }

  &:hover {
    .dropdown-content {
      display: block;
    }
  }
}



</style>