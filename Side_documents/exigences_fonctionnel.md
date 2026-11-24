## spécifications ##

- `Units` : define a tile of the game.
- `Grade` : enumerate the different types of tiles. (with her value)
- `Fight` : implement a fight against two `Units`.
- `Player` : link the two different type of player.
- `RealPlayer` : it's the human player, with the different action that he can do.
- `AIPlayer` : it's the robot player, with action who was pick randomly.
- `Game` : initialise a game with a list of `Player` and the game `Grid`.
- `Mode` : link the two games modes, `BeginnerMode` and `ClassicMode`.
- `BeginnerMode` : game mode with all information helpful during the game.
- `ClassicMode` : normal mode without help. (just the game, information need to be taken by the player)
- `Timer` : Manage the time of the game or to do an action.
- `Cell` : it's a cell of the `grid`.
- `Grid` : define game board.
 

## Exigences fonctionnel ##

Joueur : - can login and signin on the game.
         - can create a game in beginner or classic mode.
         - can modify place of his units before the start of a game.
         - can moved tiles that follow game rules.


IA : - can moved randomly her tiles that follow game rules.