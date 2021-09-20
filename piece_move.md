# Send Out a Piece Move

This endpoint This endpoint sends out a single piecemove and makes it available so that the other player and spectators can view it 

#### - Method: PATCH
#### - Description: Sends out or broadcasts a piece move to the game room

## End-Point
<details>
  <summary> [PATCH]: /api/v1/game/piecemove </summary>
  Zuri Chess plugin<br>
  https://chess.zuri.chat/api/v1/game/piecemove
</details>

## Parameters
-None

## Request Body Schema
| Name | Data type | Description|
| ------ | ------ |-------------|
| player_id | string |The user_id of the player that makes the move|
| position_fen | string |the FEN state of the game|
| game_id | string |the game id|
| board_state | string |the state of the board after the move is made|

### Example
```sh
{
  "player_id": <user_id>,
  "position_fen": "A1-A2",
  "game_id": "string",
  "board_state": "string"
}
```

## Responses
### Success
``` sh
Code: 200
Description: Success, the piece move was recorded and saved successfully
{
  "message": "pieced moved",
  "data": {} // game_id and move success
  "success": true
}
```

### Error
``` sh
Code: 400
Description: Error, the game as specified by the given game id was not found in the database
{
  "message": "Game not found",
  "data": null
  "success": false
}
```

### Error
``` sh
Code: 400
Description: Error. Wrong player_id. the move was sent from an unidentified user or a user who is not playing in the game.
{
  "message": "Only players are allowed to make moves",
  "data": null
  "success": false
}
```

### Internal error
```sh
Code: 500
Description: Internal server error occured
{
  "message": "Failed to move piece",
  "data": null,
  "success": false
}
```
