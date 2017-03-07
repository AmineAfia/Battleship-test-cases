Pre-interop Test (Groupe 4)
===================================

Wir haben uns mit Groupe 4 für drei mal getroffen. 
Für die drei Termine haben wir in Info-Bau getroffen und haben Benjamins Switch benutzt.

- Am 09.02.17
    - Ziel:
        - Erste Test auch wenn wir nicht alles fertig haben.
    - Bugs:
        - Kleine Bugs in Server. (z.B. Server hat dummy spiele am Anfang geschickt (sofort behoben))
        - Client konnte nicht richtig plazieren, shiessen und moven (wurde nach dem treffen gefixed)
- Am 18.02.17
    - Ziel:
        - Test der Client/Server funktionalitäten mit ein ander.
    - Bugs:
        - (x,y) waren getaucht
        - Client hat nicht alle nachrichten richtig gehandelt, (wurde beim Treffen gefixed und nach dem Treffen verbessert)
        - Neue test-cases entdenkt (z.B was passiert wenn ein Schiff in ein geschaussene feld fährt)
- Am 23.02.17
    - Ziel:
        - Unsere Client und Server waren fertig. Wir wollten die aber mit den test-cases in den Tabellen unten testen.
    - Bugs:
        - Kleine UI bugs, die wir danach gefixed haben.

##### Am ende hat alles einwandfrei funktioniert und konnten miteinander spielen.

------------------------------------------------------------------------------------------------------------

Client's Tests
================

Lobby related
---------------------

| Create_Game Test|  Correct Response   |
|-----------------------------------------------------------------------|--------------|
| Correct create| 			✔        |
| Delete game when user lose connection| 			✔        |
| Cancel message| 			✔        |

| Join_Game Test|  Correct Response   |
|-----------------------------------------------------------------------|--------------|
| Correct join| 			✔        |
| The Game is full| 			✔        |
| The Game doesn't exist| 			✔        |
| Correct Join with password| 			✔        |

Game related
---------------------

| Ship_Placement Test                                                                  |  Correct Response   |
|-----------------------------------------------------------------------|--------------|
| Correct ship placement                                                          | 			✔        |
| The ship palcement has overlaping ships                                          | 			✔        |
| Too Many Ships are placed                                         | 			✔        |

| Move Test                                                                  |  Correct Response   |
|-----------------------------------------------------------------------|--------------|
| Correct move                                                          | 			✔        |
| The move has illegal ship_id                                          | 			✔        |
| The move exceeds the game_boundry                                          | 			✔        |
| A ship is moved next to another one                                         | 			✔        |
| A ship can’t be moved                                             | 			✔        |
| A ship is moved on shooted (with FAIL) field                      | 			✔        |
| Ship collision                                                    | 			✔        |

|  shoot Test                                                                  |  Correct Response   |
|-----------------------------------------------------------------------|--------------|
| The  shoot is out of game_boundry                                 | 			✔        |
| can’t shoot already HIT position| 			✔        |
| unlimited shooting in a FAIL shooting position| 			✔        |


Testing Protocol
================

Server Tests
------------

Each test uses the server of one team and a client of both teams.

###  Basic game management

| Test                                                                  |  G4 Server   |  G8 Server   | 
|-----------------------------------------------------------------------|---------------|---------------|
|Get GAMES                                                          | ✔             | ✔             |
|Game create successful                                                 | ✔             | ✔             |
|Game join successful                                                   | ✔             | ✔             |
|Server deletes created game when client leaves                         | ✔             | ✔             |
|Wait for opponent                                                      | ✔             | ✔             |
|Place ships successful                                                 | ✔             | ✔             |
|Wait for own turn                                                      | ✔             | ✔             |
|Run multiple games at the same server at the same time                 | ✔             | ✔             |


###  Different game endings

| Test                                                                  |  G4 Server   |  G8 Server   |
|-----------------------------------------------------------------------|---------------|---------------|
|Game ends: one wins and one loses                                      | ✔             | ✔             |
|Abort game                                                             | ✔             | ✔             |

###  Chat

| Test                                                                  |  G4 Server   |  G8 Server   |
|-----------------------------------------------------------------------|---------------|---------------|
|Client sends message                                                   | ✔             | ✔             |
|All clients receive the message                                        | ✔             | ✔             |
