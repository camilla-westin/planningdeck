<template>
  <div class="card">
    <span class="complexity-num">{{ msg }}</span>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../scss/card.scss';
</style>
