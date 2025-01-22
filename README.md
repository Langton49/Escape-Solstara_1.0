# ESCAPE SOLSTARA
Escape Solstara is a multiplayer scavenger hunt game set in a medieval-themed city. Players must compete against each other to find a series of hidden artifacts, guided by riddles that lead them from one artifact to the next. The goal of the game is to be the first to find all the artifacts and reveal a secret passphrase, which grants passage out of the city gates.

**Link To Build Folder:** https://drive.google.com/drive/folders/1cA3443J4xZ-ED0Oge7mBRLtq1yLPYdjz?usp=drive_link 

**Link To Project:** https://github.com/Langton49/ES_project

## Features
- Multiplayer Gameplay: Compete with other players to solve riddles and find artifacts.
- Dynamic Scavenger Hunts: Riddles are dynamically generated using the ChatGPT API, ensuring a unique experience every time.
- Chatbot Assistance: Players can interact with an in-game chatbot to receive hints and guidance on solving riddles and locating hidden artifacts.
- Medieval City Exploration: Explore various locations in a medieval-themed city as you search for the hidden items.

## Technologies
- Unity: The game is built using Unity, providing the immersive 3D environment for the medieval city.
- AWS GameLift: Used to manage multiplayer sessions and real-time communication between players.
- AWS Lambda: Handles matchmaking and game session management.
- AWS Cognito: Provides secure authentication and temporary credentials for players.
- ChatGPT API: Powers dynamic riddle generation, ensuring each game session offers a new challenge.

## How To Play:
### Install
- Download the build folder through the link above.
- Find the Escape Solstara zip folder and unzip it.
- Launch the Escape Solstara.exe file.
### In-Game
- Enter the desired number of players and specify how many artifacts each player must find before revealing the passphrase.
- The game will wait for all players to join before presenting the first riddle.
- Each riddle leads to an artifact hidden within the city.
- Explore the city to find the artifact, which will be marked by a glowing green arrow when you’re nearby.
- Once all required artifacts are collected, the passphrase will be revealed.
- Approach any statue in the city and enter the passphrase.
- If correct, you’ll gain the ability to approach a city gate and escape.
- Each player has access to a chatbot for assistance with riddles or deciphering the passphrase without collecting all artifacts.



