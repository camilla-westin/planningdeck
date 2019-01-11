<template>
  <div id="app">
    <img src="./assets/logo.svg" width="200" alt="Chas logotype" />
    <h1>Planning poker</h1>
    <Deck />
  </div>
</template>

<script>
import Deck from './components/Deck.vue'

export default {
  name: 'app',
  components: {
    Deck
  }
}
</script>

<style lang="scss">
  @import './scss/layout.scss';
</style>
