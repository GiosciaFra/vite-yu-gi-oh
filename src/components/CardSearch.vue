<script>

import { store } from '../store';
import axios from 'axios';

export default {
    name: 'CardSearch',

    data() {
        return {
        store,
        }
  },

  methods: {
    selectArchetype(archetypeName) {
      this.store.selectItem = archetypeName;
      this.$emit('search', archetypeName);
    },
  },

  
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        this.store.archetypeList = res.data;
      });
  },

}
</script>

<template>
<div class="container">
    <div class="dropdown">
    <button class="dropdown-btn">Select Archetype</button>
    <ul class="dropdown-content">
            <li @click="selectArchetype(archetype.archetype_name)" 
            v-for="archetype in store.archetypeList" 
            class="dropdown-item">{{ archetype.archetype_name }}</li>
    </ul>
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
    padding: 10px 20px;
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
    overflow-y: scroll;
    max-height: 300px;
    cursor: pointer;

    li {
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