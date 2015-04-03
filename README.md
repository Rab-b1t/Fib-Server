# Fib-Server
Fib Server - Temporary (rough) layout of back-end functionality

Server API Restful Spec.
---------------------------
GET - Friends list (along with game status (time/score) if currently playing)
GET - Score/level
POST - Send game invitation to friend
POST - Accept game invitation from friend
POST - Reject game invitation from friend
GET - Time remaining for individual game
GET - Current round number
POST - Answer to individual round (update game status on backend)
GET - Result from answer to individual round
GET - Fib and quips for individual round
GET - One[Two if available]-sided game results upon completion of all rounds
POST - Game results upon completion of all rounds (both-ways)

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
