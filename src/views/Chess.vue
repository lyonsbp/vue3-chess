<template>
  <div class="game">
    <ChessBoard :boardSize="8" :piecesMap="piecesMap" />
  </div>
</template>

<script>
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
        else if (i === 0) {
          if (j === 0) piecesMap[i][j] = "R";
          if (j === 1) piecesMap[i][j] = "N";
          if (j === 2) piecesMap[i][j] = "B";
          if (j === 3) piecesMap[i][j] = "Q";
          if (j === 4) piecesMap[i][j] = "K";
          if (j === 5) piecesMap[i][j] = "B";
          if (j === 6) piecesMap[i][j] = "N";
          if (j === 7) piecesMap[i][j] = "R";
        } else if (i === 7) {
          if (j === 0) piecesMap[i][j] = "R";
          if (j === 1) piecesMap[i][j] = "N";
          if (j === 2) piecesMap[i][j] = "B";
          if (j === 3) piecesMap[i][j] = "K";
          if (j === 4) piecesMap[i][j] = "Q";
          if (j === 5) piecesMap[i][j] = "B";
          if (j === 6) piecesMap[i][j] = "N";
          if (j === 7) piecesMap[i][j] = "R";
        } else {
          piecesMap[i][j] = "";
        }
      }
    }

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
