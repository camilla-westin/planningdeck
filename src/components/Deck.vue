<template>
  <div id="deck">
      <div class="cards">
        <div v-for="card in cardsList" :key="card.index" v-on:click="selectCard(card)" class="card-wrap" v-bind:class="{'selected' : card.selected }"> 
            <div v-if="card.revealed" class="card card-front">
                <span class="complexity">{{ card.complexity }}</span>
            </div>
            <div v-else class="card card-back">
                <img src="../assets/logo.svg" width="90" alt="Chas logotype" />
                <span>Click to reveal card</span>
            </div>
        </div>
      </div>
      <button id="restart" v-on:click="reLoad()">Start over</button>
  </div>
</template>

<script>
var cards = 
[
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

export default {
  name: 'Deck',
  data() {
      return {
          //Get card data from array
          cardsList: cards
      }
  },
  methods: {
      selectCard: function(card) {

        //Hide all cards
        var cardElement = document.getElementsByClassName('card-wrap');

        for (var i = 0; i < cardElement.length; ++i) {
            cardElement[i].classList.add('hidden');
        }

        //Change class on clicked card to selected to show it
        card.selected = !card.selected;

        // Toggle card. When first selected it will show backside then it can be toggled.
        card.revealed = !card.revealed;

        //Show restart button
        document.getElementById('restart').style.display = 'block';            
      },
      reLoad: function() {
        //Reload page to start again  
        window.location.reload();
      }
  }


}
</script>

<style lang="scss">
      @import '../scss/deck.scss';
</style>
