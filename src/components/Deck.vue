<template>
  <div id="deck">
      <div class="cards">
        <div v-for="card in cards" :key="card.index" class="card">
            <span class="complexity">{{ card.complexity }}</span>
        </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'Deck',
  data() {
      return {
          cards: [
            { complexity: '1' } ,
            { complexity: '2' },
            { complexity: '3' },
            { complexity: '5' },
            { complexity: '8' },
            { complexity: '13' },
            { complexity: '20' },
            { complexity: '40' },
            { complexity: '100' },
            { complexity: "I don't know" },
        ]
      }
  }

}
</script>

<style lang="scss">
      @import '../scss/deck.scss';
</style>
