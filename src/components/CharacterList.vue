<template>
<div>
    <ul>
        <selected-character  v-for="(character, index) in characters" :character="character" :key="index"></selected-character>
    </ul>
</div>
  
</template>

<script>
import SelectedCharacter from './CharacterSelect.vue'

export default {
    name: 'character-list',
    props: ['characters'],
    components: {
        'selected-character': SelectedCharacter
    }

}
</script>

<style>

</style>