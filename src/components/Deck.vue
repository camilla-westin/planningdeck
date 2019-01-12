<template>
  <div id="deck">
      <div class="cards">
        <div v-for="card in cards" :key="card.index" v-on:click="revealCard(card)" class="card-wrap"> 
            <transition name="flip">
                <div v-if="card.revealed" class="card card-front" key="card-front">
                    <span class="complexity">{{ card.complexity }}</span>
                </div>
                <div v-else class="card card-back" key="card-back">
                    <span class="back">Reveal on click</span>
                </div>
            </transition>
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
            { complexity: '0', revealed: false, selected: false } ,
            { complexity: '1', revealed: false, selected: false } ,
            { complexity: '2', revealed: false, selected: false },
            { complexity: '3', revealed: false, selected: false },
            { complexity: '5', revealed: false, selected: false },
            { complexity: '8', revealed: false, selected: false },
            { complexity: '13', revealed: false, selected: false },
            { complexity: '20', revealed: false, selected: false },
            { complexity: '40', revealed: false, selected: false },
            { complexity: '100', revealed: false, selected: false },
            { complexity: '?', revealed: false, selected: false },
            { complexity: '∞', revealed: false, selected: false }
        ]
      }
  },
  methods: {
      revealCard: function(card) {
         card.revealed = !card.revealed; 
      }
  }

}
</script>

<style lang="scss">
      @import '../scss/deck.scss';
</style>
