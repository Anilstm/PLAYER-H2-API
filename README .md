Contains five files,

- `PlayerController.java`
- `PlayerRepository.java`
- `PlayerH2Service.java`
- `PlayerRowMapper.java`
- `Player.java`
Contains a database file `cricketteam` which contains `TEAM` table.

#### TEAM Table

|   Columns    |  Type   |
| :----------: | :-----: |
|   playerId   | INTEGER |
|  playerName  |  TEXT   |
| jerseyNumber | INTEGER |
|     role     |  TEXT   |


### Completed Instructions

- `Player.java`: `Player` class contains the following attributes.

    |  Attribute   |  Type  |
    | :----------: | :----: |
    |   playerId   |  int   |
    |  playerName  | String |
    | jerseyNumber |  int   |
    |     role     | String |

- `PlayerRepository.java`: Creates an `interface` containing required methods.
- `PlayerService.java`: Updates the service class with logic for managing player data.
- `PlayerController.java`: Creates the controller class to handle HTTP requests.
- `PlayerRowMapper.java`: Creates a class which implements the `Rowmapper Interface`.

Implemented the following APIs.

### API 1

#### Path: `/players`

#### Method: `GET`

#### Description:

Returns a list of all players in the team.

#### Response

```
[
    {
        "playerId": 1,
        "playerName": "Alexander",
        "jerseyNumber": 5,
        "role": "All-rounder"
    },
   ...
]
```

### API 2

#### Path: `/players`

#### Method: `POST`

#### Description:

Creates a new player in the `team`. The `playerId` is auto-incremented.

#### Request

```
{
  "playerName": "Prince",
  "jerseyNumber": 24,
  "role": "Bowler"
}
```

#### Response

```
{
    "playerId": 12,
    "playerName": "Prince",
    "jerseyNumber": 24,
    "role": "Bowler"
}
```

### API 3

#### Path: `/players/{playerId}`

#### Method: `GET`

#### Description:

Returns a player based on the `playerId`. If the given `playerId` is not found in the `team`, raise `ResponseStatusException` with `HttpStatus.NOT_FOUND`.


#### Success Response

```
{
    "playerId": 1,
    "playerName": "Alexander",
    "jerseyNumber": 5,
    "role": "All-rounder"
}
```

### API 4

#### Path: `/players/{playerId}`

#### Method: `PUT`

#### Description:

Updates the details of a player in the team based on the `playerId`.  Also, return the updated player details from the `TEAM` using the `playerId`.


#### Request

```
{
    "playerName": "Yuvi"
    "jerseyNumber": 12,
    "role": "All-rounder"
}
```

#### Success Response

```
{
    "playerId": 3,
    "playerName": "Yuvi",
    "jerseyNumber": 12,
    "role": "All-rounder"
}
```

### API 5

#### Path: `/players/{playerId}`

#### Method: `DELETE`

#### Description:

Deletes a player from the team  based on the `playerId`. 
