<template>
  <div class="game">
    <InfoBoard :gameState="gameState" />
    <ChessBoard
      :boardSize="8"
      :gameState="gameState"
      @cell-clicked="handleClick"
    />
  </div>
</template>

<script>
import ChessBoard from "@/components/ChessBoard";
import InfoBoard from "@/components/InfoBoard";
export default {
  name: "Chess",
  components: {
    ChessBoard,
    InfoBoard
  },
  methods: {
    handleClick({ row, col, piece }) {
      console.log({ row, col, piece });
      if (piece.owner === this.gameState.currentPlayer) {
        const player = piece.owner;
        console.log(player, "this is my piece");
        if (player === 1) {
          if (piece.symbol === "P") {
            console.log();
          }
        }
      }
    }
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
          piece.cellActive = false;
        } else if (i === 6) {
          piece.owner = 2;
          piece.symbol = "P";
          piece.name = "Pawn";
          piece.cellActive = false;
        } else if (i === 0) {
          piece.owner = 1;
          if (j === 0) {
            piece.symbol = "R";
            piece.name = "Rook";
            piece.cellActive = false;
          }
          if (j === 1) {
            piece.symbol = "N";
            piece.name = "Knight";
            piece.cellActive = false;
          }
          if (j === 2) {
            piece.symbol = "B";
            piece.name = "Bishop";
            piece.cellActive = false;
          }
          if (j === 3) {
            piece.symbol = "Q";
            piece.name = "Queen";
            piece.cellActive = false;
          }
          if (j === 4) {
            piece.symbol = "K";
            piece.name = "King";
            piece.cellActive = false;
          }
          if (j === 5) {
            piece.symbol = "B";
            piece.name = "Bishop";
            piece.cellActive = false;
          }
          if (j === 6) {
            piece.symbol = "N";
            piece.name = "Knight";
            piece.cellActive = false;
          }
          if (j === 7) {
            piece.symbol = "R";
            piece.name = "Rook";
            piece.cellActive = false;
          }
        } else if (i === 7) {
          piece.owner = 2;
          if (j === 0) {
            piece.symbol = "R";
            piece.name = "Rook";
            piece.cellActive = false;
          }
          if (j === 1) {
            piece.symbol = "N";
            piece.name = "Knight";
            piece.cellActive = false;
          }
          if (j === 2) {
            piece.symbol = "B";
            piece.name = "Bishop";
            piece.cellActive = false;
          }
          if (j === 3) {
            piece.symbol = "K";
            piece.name = "King";
            piece.cellActive = false;
          }
          if (j === 4) {
            piece.symbol = "Q";
            piece.name = "Queen";
            piece.cellActive = false;
          }
          if (j === 5) {
            piece.symbol = "B";
            piece.name = "Bishop";
            piece.cellActive = false;
          }
          if (j === 6) {
            piece.symbol = "N";
            piece.name = "Knight";
            piece.cellActive = false;
          }
          if (j === 7) {
            piece.symbol = "R";
            piece.name = "Rook";
            piece.cellActive = false;
          }
        } else {
          piece.symbol = "";
          piece.name = "";
          piece.cellActive = false;
          piece.owner = null;
        }
        piecesMap[i][j] = piece;
      }
    }

    const gameState = {
      currentPlayer: 1,
      isPlayer1InCheck: false,
      isPlayer2InCheck: false,
      piecesMap
    };

    return {
      boardSize,
      gameState
    };
  }
};
</script>

<style>
.game {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
