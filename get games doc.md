# Get all games

This endpoint returns a list of all the games available in the database. 

#### - Method: Get
#### - Description: returns all game objects in the database

## End-Point
<details>
  <summary> [GET]: /api/v1/game/all </summary>
  Zuri chat plugin API <br>
  https://chess.zuri.chat/api/v1/game/all
</details>

## Required parameters;
-None

## Optional parameters;
| Name | Data type | Description|
| ------ | ------ |-------------|
| ongoing | integer |filters to return all games that have started|
| noPlayer2  | integer |filters to get all games that don't have player 2|

### Games can be filtered based on status by adding preset parameters to the url.
- set ['noPlayer2'= 1] to get all games that don't have player 2
- set ['ongoing' = 1] to get all games that have started 

## Responses
### Success
``` sh
Code: 200
Description: Success, return list of all games in JSON object format
{
  "message": "Games retrieved successfully",
  "data": "{}", //list of game objects
  "success": true
}
```

### Internal error
```sh
Code: 500
Description: Internal server error occured
{
  "message": "Unable to get all Games",
  "data": null,
  "success": false
}
```
# Examples
#### Get all games in db
```sh
[GET]: https://chess.zuri.chat/api/v1/game/all
```
#### Get all games in db that don't have player 2
```sh
[GET]: https://chess.zuri.chat/api/v1/game/all?noPlayer2=1
```
#### Get all games in db that have started i.e currently ongoing games 
```sh
[GET]: https://chess.zuri.chat/api/v1/game/all?ongoing=1
```
