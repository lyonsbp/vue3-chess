<template>
  <div class="symbol-text">
    {{ pieceSymbol }}
  </div>
</template>

<script>
export default {
  props: {
    pieceSymbol: String
  },
  setup() {
    return {};
  }
};
</script>

<style>
.symbol-text {
  color: red;
  font-weight: bold;
}
</style>
