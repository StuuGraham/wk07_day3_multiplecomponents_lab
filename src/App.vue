<template>
<div>
  <h1>Rick and Morty Characters</h1>
  <character-list :characters="characters"></character-list>
  <character-detail :character="selectedCharacter"></character-detail>
</div>
  
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';
import {eventBus} from './main.js';


export default {
  name: 'app',
  data() {
    return {
      characters: [],
      selectedCharacter: null

    };
  },

  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characters = characters.results);

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    })
  },

  components: {
    'character-list': CharacterList,
    'character-detail': CharacterDetail

  }


}
</script>

<style>

</style>