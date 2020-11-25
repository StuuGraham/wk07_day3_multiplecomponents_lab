<template>
  <div v-if="character">
      <h3>{{character.name}}</h3>
      <br>
      <p>Species: {{character.species}}</p>
      <p>Originates From: {{character.origin.name}}</p>
      <p>Episode Features: {{character.episode.length}}</p>
      <br>
      <img class="character-img" :src="character.image"/>
  </div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>
 .character-img {
     height: 250px;
     width: 200px;
 }
</style>