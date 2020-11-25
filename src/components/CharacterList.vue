<template>
<div>
    <!-- <ul>
        <selected-character  v-for="(character, index) in characters" :character="character" :key="index"></selected-character>
    </ul> -->
        <label for="character_select">Select a Character:</label>
        <br>
        <select id="character_select" v-on:change="handleSelect" v-model="selectedCharacter">
            <option disabled value="">Select a character</option>
            <option v-for="(character, index) in characters" :value="character" :key="index">{{character.name}}</option>
        </select>
        <br>
        <br>
        <p>
        <label for="character_select">Search:</label>
        </p>
        <input type="text" v-model="characterSearch" placeholder="Search for a Character">
        <button on:click="handleSearch">Submit</button>
</div>
  
</template>

<script>
import { eventBus } from '../main'
import SelectedCharacterComp from './CharacterSelect.vue'

export default {
    name: 'character-list',
    props: ['characters'],
    data() {
        return {
            'selectedCharacter': {},
            'characterSearch': ""
        }
    },
    components: {
        'selected-character': SelectedCharacterComp
    },
    methods: {
        handleSelect(){
            eventBus.$emit('character-selected', this.selectedCharacter);

        },
        handleSearch(){
            eventBus.$emit('character-selected', this.characterSearch);
        },
    }

}
</script>

<style>

</style>