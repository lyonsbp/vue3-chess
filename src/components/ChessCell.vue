<template>
  <div class="symbol-text" :class="piece.owner === 1 ? 'player-1' : 'player-2'">
    {{ piece.symbol }}
  </div>
</template>

<script>
export default {
  props: {
    piece: Object
  },
  setup() {
    return {};
  }
};
</script>

<style>
.symbol-text {
  font-weight: bold;
}
.player-1 {
  color: red;
}
.player-2 {
  color: black;
}
</style>
