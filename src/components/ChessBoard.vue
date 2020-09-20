<template>
  <div class="board" v-if="piecesMap[0]">
    <template v-for="row in boardSize" :key="row">
      <Cell
        v-for="col in boardSize"
        :key="col"
        class="cell"
        :class="{ colored: isColored(row, col) }"
        :pieceSymbol="piecesMap[row - 1][col - 1]"
      ></Cell>
    </template>
  </div>
</template>

<script>
import Cell from "../components/ChessCell.vue";
export default {
  components: {
    Cell
  },
  props: ["boardSize", "piecesMap"],
  setup(props) {
    function isColored(row, col) {
      const colIsOdd = col % 2;
      const rowIsOdd = row % 2;

      return rowIsOdd ? colIsOdd : !colIsOdd;
    }

    console.log(props.piecesMap);

    return {
      isColored
    };
  }
};
</script>

<style>
.cell {
  height: 100%;
  width: 100%;
}
.colored {
  background-color: lightgray;
}
.board {
  --board-size: 25px;
  display: grid;
  grid-template-columns: repeat(8, var(--board-size));
  grid-template-rows: repeat(8, var(--board-size));
  border: 2px solid black;
}
</style>
