<template>
  <div id="deck">
      <div class="cards">
        <div v-for="card in cards" :key="card.index" v-on:click="selectCard(card)" class="card-wrap" v-bind:class="{'selected' : card.selected }"> 
            <transition name="flip">
                <div v-if="card.revealed" class="card card-front">
                    <span class="complexity">{{ card.complexity }}</span>
                </div>
                <div v-else class="card card-back">
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
            { complexity: '0', revealed: true, selected: false } ,
            { complexity: '1', revealed: true, selected: false } ,
            { complexity: '2', revealed: true, selected: false },
            { complexity: '3', revealed: true, selected: false },
            { complexity: '5', revealed: true, selected: false },
            { complexity: '8', revealed: true, selected: false },
            { complexity: '13', revealed: true, selected: false },
            { complexity: '20', revealed: true, selected: false },
            { complexity: '40', revealed: true, selected: false },
            { complexity: '100', revealed: true, selected: false },
            { complexity: '?', revealed: true, selected: false },
            { complexity: '∞', revealed: true, selected: false }
        ]
      }
  },
  methods: {
      selectCard: function(card) {
        //Hide all cards
        var cardElements = document.getElementsByClassName('card-wrap')

        for (var i = 0; i < cardElements.length; ++i) {
            cardElements[i].classList.add('hidden');
        }

        //Change class on clicked card to selected
        card.selected = !card.selected;

        // Flip card and show backside
        card.revealed = !card.revealed;
        
        //If card has .selected class
        if(card.classList.contains('selected')) {
            // Show selected card
            card.style.display = 'block';
            
            //Reveal card on click if card is already selected.
            card.revealed = !card.revealed;

            //Todo: Back button
        }
      }
  }
}
</script>

<style lang="scss">
      @import '../scss/deck.scss';
</style>
