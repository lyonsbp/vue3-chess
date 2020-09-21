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
        const piece = {
          symbol: "",
          name: "",
          owner: null
        };
        if (i === 1) {
          piece.owner = 1;
          piece.symbol = "P";
          piece.name = "Pawn";
        } else if (i === 6) {
          piece.owner = 2;
          piece.symbol = "P";
          piece.name = "Pawn";
        } else if (i === 0) {
          piece.owner = 1;
          if (j === 0) {
            piece.symbol = "R";
            piece.name = "Rook";
          }
          if (j === 1) {
            piece.symbol = "N";
            piece.name = "Knight";
          }
          if (j === 2) {
            piece.symbol = "B";
            piece.name = "Bishop";
          }
          if (j === 3) {
            piece.symbol = "Q";
            piece.name = "Queen";
          }
          if (j === 4) {
            piece.symbol = "K";
            piece.name = "King";
          }
          if (j === 5) {
            piece.symbol = "B";
            piece.name = "Bishop";
          }
          if (j === 6) {
            piece.symbol = "N";
            piece.name = "Knight";
          }
          if (j === 7) {
            piece.symbol = "R";
            piece.name = "Rook";
          }
        } else if (i === 7) {
          piece.owner = 2;
          if (j === 0) {
            piece.symbol = "R";
            piece.name = "Rook";
          }
          if (j === 1) {
            piece.symbol = "N";
            piece.name = "Knight";
          }
          if (j === 2) {
            piece.symbol = "B";
            piece.name = "Bishop";
          }
          if (j === 3) {
            piece.symbol = "K";
            piece.name = "King";
          }
          if (j === 4) {
            piece.symbol = "Q";
            piece.name = "Queen";
          }
          if (j === 5) {
            piece.symbol = "B";
            piece.name = "Bishop";
          }
          if (j === 6) {
            piece.symbol = "N";
            piece.name = "Knight";
          }
          if (j === 7) {
            piece.symbol = "R";
            piece.name = "Rook";
          }
        } else {
          piecesMap[i][j] = "";
        }
        piecesMap[i][j] = piece;
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
