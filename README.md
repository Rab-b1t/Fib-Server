# Fib-Server
Fib Server - Temporary (rough) layout of back-end functionality

Server API Restful Spec.
---------------------------
GET - /api/user/friends - Friends list (along with game status (time/score) if currently playing)
GET - /api/user/score - Score/level
POST - /api/game/invite/:friendid - Send game invitation to friend
POST - /api/game/accept/:friendid - Accept game invitation from friend
POST - /api/game/reject/:friendid - Reject game invitation from friend
GET - /api/game/time/:friendid - Time remaining for individual game
GET - /api/game/round/:friendid - Fib and quips for individual round, along with round number
POST - /api/game/round/:friendid - Answer to current individual round (update game status on backend)
GET - /api/game/round/:friendid/:round - Result from answer to individual round
GET - /api/game/:friendid - One[Two if available]-sided game results upon completion of all rounds

Flow
---------------------------
Login
See friends list
See your score/level

+--[ To initiate game ]
| Request game with friend
| Accept game from friend
| Reject game from friend
+--

+--[ To play game ]
| Ensure you're within time limit of game
| Display two quips, one fib (ensure within round limit)
| Display result of your set of rounds
|  +- If opponent finished, display their results
| Display status of game on friends list
|  +- Client-side toggle for all friends (including current opponents)
|  +- Or display only current games, etc.
| Store result of game
| Save answer to round
| Display correctness of answer to round
+--

Display past game results

In Progress
---------------------------
GET - Friends list (along with game status (time/score) if currently playing)
GET - Score/level
