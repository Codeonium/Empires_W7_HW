<template lang="html">
  <div id="favourite_civilizations">
    <h2>Favourite Civilizations</h2>
    <ul>
      <li v-for="favouriteCivilization in favouriteCivilizations">{{favouriteCivilization.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-civilizations',
  props: ['favouriteCivilizations']
}
</script>

<style lang="css" scoped>
</style>
