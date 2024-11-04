# A Solidity coding sample - Rock Paper Scissors

## A Solidity coding sample - Rock Paper Scissors
This smart contract implements a secure Rock-Paper-Scissors game in Solidity, ready to be deployed on the Ethereum blockchain. The game follows these steps:

1. Two players register and place a bet.
2. Each participant picks a move and a password. They send the hash of the concatenated string to the contract which stores it.
3. When the two players have committed their moves, they reveal what they have played. To do so, they send their move and password in clear. The contract verifies that the hash of the received input matches the one stored.
4. When both player have revealed their move, the contract determines the winner and sends him/her the total betting pool. If there is a draw, each player gets their bet back.
5. The game resets and can be played again by new players.

## SHA256 genereator
https://tools.keycdn.com/sha256-online-generator

## Usage

1. Register with function `register()`. You must send a bet greater than or equal to both the minimum `BET_MIN` and to the first player's bet (if defined).
2. Commit a move with function `play(bytes32 encrMove)`. The format of the expected input is `"0xHASH"` where `HASH` is the SHA256 hash of a string `move-password`. `move` is an integer ranging from 1 to 3 which correspond to rock, paper and scissors respectively and `password` is a string that should be kept secret.
3. Only when you and your opponent have played, you can reveal your move with `reveal(string memory clearMove)`. The format of the expected input is `"move-passord"`.
4. When both players have revealed their move or when the reveal phase has ended, you can get the result and the reward via `getOutcome()`.

In the screenshots, player A and player B (who initially own 100 ethers each) have bet 10 ethers. Player A played rock while player B chose scissors. At the end of the game, player A won the total contract's balance.

