basic racing game mode

setup is as follows:

racingGame::pickPlayerSpawnPoint injects a search for a spawn point within a raceline group
up to 4 players join, each using the next spawner in that group

countdown ensues either by hitting the max players or waiting long enough since the first joined

RacingTrigger's each have a .order variable tested against to ensure players are moving in the correct direction
on hitting the last (determined by the racingGame::GetMaxTriggers() which polls the racingTriggers group)

on completion of the scripted 3 laps by the first contestant, 1 minute is given for others to complete before racingGame::finishRace triggers score lock in

during that process, the highScoreList arrayobject adds, sorts and prunes the top 10 scores, then sends the resulting list to clients
