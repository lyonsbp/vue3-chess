<template>
  <div class="game">
    <ChessBoard :boardSize="8" :piecesMap="piecesMap" />
  </div>
</template>

<script>
console.log("hello");
import ChessBoard from "@/components/ChessBoard";
export default {
  name: "Chess",
  components: {
    ChessBoard
  },
  setup() {
    const piecesMap = [];
    const boardSize = 8;
    for (let i = 0; i < boardSize; i++) {
      piecesMap[i] = [];
      for (let j = 0; j < boardSize; j++) {
        if (i === 1 || i === 6) piecesMap[i][j] = "P";
        else piecesMap[i][j] = "";
      }
    }
    console.log(piecesMap);

    return {
      boardSize,
      piecesMap
    };
  }
};
</script>

<style>
.game {
  display: flex;
  justify-content: center;
}
</style>
