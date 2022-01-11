Given the chess moves list, it gives the final squares of the pieces. 

Why was this needed: chess.js doesn't track individual pieces and it's 
difficult to track using the chess.js methods as it only gives the piece,
but not the original square of the piece.

## Example Code


```js
import { processGame } from "chess.js-track-pieces";
let chessMoves = `1. d4 Nc6 2. Nf3 d5 3. Nc3 g6 4. e3 Nf6 5. Bd3 Bg7 6. e4 e6 7. e5 Ng4 8. Ng5 Nxd4 9. Qxg4 c5 10. O-O Bxe5 11. f4 Bf6 12. Na4 e5 13. fxe5 Bxg4 14. exf6 c4 15. Re1+ Kf8 16. Bxc4 Nxc2 17. Rb1 Nxe1 18. Bd2 Nc2 19. Bd3 Qc7 20. Rc1 Bf5 21. Rxc2 Qe5 22. Bb4+ Kg8 23. Re2 Qxf6`;
let res = processGame(chessMoves, { verbose: true });
console.log(res);

/* Output 
 {
originalSquare: 'finalSquareOfThatPiece'
...
}
*/
{
  d2: 'd4',
  g8: 'g4',
  e2: 'e5',
  e7: 'e5',
  d1: 'g4',
  f8: 'f6',
  c7: 'c4',
  c2: 'c2',
  h1: 'e1',
  b8: 'c2',
  f2: 'f6',
  a1: 'a1',
  b1: 'b1',
  c1: 'c1',
  e1: 'e1',
  f1: 'f1',
  g1: 'g1',
  a2: 'a2',
  b2: 'b2',
  g2: 'g2',
  h2: 'h2',
  a8: 'a8',
  c8: 'c8',
  d8: 'd8',
  e8: 'e8',
  h8: 'h8',
  a7: 'a7',
  b7: 'b7',
  d7: 'd7',
  f7: 'f7',
  g7: 'g7',
  h7: 'h7'
}
```

### processGame(chessMovesList, {verbose: false})

chessMovesList is the string of all the chess moves in the algebraic notation.
If verbose is true, it returns not just the captured pieces, but the final
squares of all the 32 pieces.

NOTE: If a pawn gets promoted, it isn't tracked further. If you wish to have
this functionality, editing the code shouldn't be hard.

If there are any issues or bugs, feel free to contribute!
