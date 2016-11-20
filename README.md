# tgmafia
Telegram mafia game bot

## Telegram Text Game Bot :: MAFIA

This is a mafia game using rules of classic mafia game covered by [icebreakerideas.com](http://icebreakerideas.com/mafia-game/)

Powered by [python telegram bot](https://github.com/python-telegram-bot/python-telegram-bot)
For website I planning to use reactjs + flask. This website should show recent game history chatlog and show whos was who.

## Basic concept
0. User texts with this bot only. Get from him basic information, where did he find this bot etc...
1. Bot sends the table of open games
2. User chooses the game to enter
3. User chooses his nickname for this game
4. After all users enter game, they get assigned their roles depends of number of active players and card they got
5. Bot anounces the game cycle: day(peasants to discuss and vote), night(mafia, detective, doctor, etc)
6. There is no vote on day 1. Only introduction cycle. The cycle ends by voting if most 51% peoples votes to end.
7. Night cycle ends by every gamemember does his action
	- Only Mafia cycle ends by voting to kill somebody
	- Every other ends by selecting another user to make interruction
8. Bot anounces to everyone that Night is over, and makes message from the user submitted templates of past night actions
10. Bot anounces discussion time. Every message got broadcasted to everyone.
11. Users select who to vote off by a command.
12. Vote cycle starts. Every one vote by a command. Vote messages are broadcasted.
13. If votes are even, then discussion starts again (goto 10).
14. After selecting one. Then another vote to verdict guilty or not. If not guilty discussion starts again (goto 10). If guilty kill.
15. If no mafia members remains then innocents win the round, else night cycle starts again (goto 7). If no innocent remains, mafia wins the round.
16. Game end, everyone get a link of history aka spectator channel. Starting poll to continue the game. If poll succeed goto 4, else goto 1 and destroy this lobby
17. Players a allowed to /leave the game and /stop the bot. They will be handled as dead person immediately.


Every role has permission to read or write messages to channels.
There are 4 main channels:
0. Spectator
1. Peasants
2. Mafia 
3. Dead 


- During day cycle, alive users's messages are broadcasted to everyone. Mafia channel is disabled (? can work through a command).
- During night cycle, alive mafia members's  messages are broadcasted to mafia and to dead. Peasants chat is disabled (? can be worked through all the way).
- Dead chat messages are broadcasted only to dead members. And only medium can read/write to them. Dead people can not read mafia chat (?). 
- Every message and action is broadcasted to spectators


## Bot requirements:
- Bot should filter commands by special roles
- Bot should be able to make polls
- Bot should be able to accept ban/kick/mute commands by administrator
- Bot should accept anouncer's story of past night by a special command
- Bot should be able to understand insults and filter them
- Bot should be able to broadcast stickers, text, replies, and not music, links, video, pictures
- Bot should support multiple lobbies, where players can group up
- Bot should provide refferal link to enter the lobby


## Planned roles:
- Innocent
- Detective
- Mafia
- Doctor
- Medium
- Ghost

## Planned for future:
- Triada
- Cupid and lovers
- Lukans
