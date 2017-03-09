Pre-interop-Test (Gruppe 4)
===================================

Wir haben uns drei Mal mit Gruppe 4 im Info-Bau getroffen.
Zum Testen haben wir Benjamins Switch benutzt.

- Am 09.02.17
    - Ziel:
        - Erste Tests, auch wenn beide Gruppen noch nicht alles fertig haben.
    - Bugs:
        - Kleine Bugs in Server. Unter anderem: Server hat noch Dummyspiele geschickt (sofort behoben) 
        - Client konnte nicht richtig platzieren, schiessen und moven (wurde nach dem Treffen gefixt)
- Am 18.02.17
    - Ziel:
        - Test der Client/Server-Funktionalitäten mit 
    - Bugs:
        - (x,y) waren vertauscht
        - Client hat nicht alle Nachrichten richtig verarbeitet, (wurde beim Treffen schnell gefixt und nach dem Treffen verbessert)
        - Neue Test-Cases entdenkt (z.B. was passiert wenn ein Schiff in ein schon beschossenes Feld fährt)
- Am 23.02.17
    - Ziel:
        - Unsere Client und Server waren fertig. Wir wollten die aber mit den Test-Cases in den Tabellen unten testen.
    - Bugs:
        - Kleine UI bugs, die wir danach gefixed haben.

##### Am Ende hat alles einwandfrei funktioniert und wir konnten miteinander spielen.

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
| The ship placement has overlaping ships                                          | 			✔        |
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
