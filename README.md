# ESCAPE SOLSTARA 🏃‍♀️💨🏰
![alt text](https://github.com/Langton49/Escape-Solstara_1.0/blob/main/Assets/Title.png "Title Card")

## Table of Contents 📑
1. [Overview](#overview)
2. [Links](#links)
3. [How I Made It](#how-i-made-it)
    1. [Tech Stack](#tech-stack)
    2. [Features](#features)
       1. [Goal](#goal)
       2. [Dynamic Riddle Generation](#dynamic-riddle-gen)
       3. [The Guardian](#guardian)
       4. [Multiplayer](#multiplayer)
5. [How To Play](#how-to-use)
    1. [Install](#install)
    2. [In-Game](#in-game)
6. [Contributing](#contributing)
7. [Credits](#credits)
8. [Contact](#contact)

## Overview 🧙‍♂️ <a name="overview">
Ah, I see you’ve found yourself trapped within the mystical walls of Solstara, curious adventurer. Welcome, though I must warn you—escape will not come easily. 
Scattered across this marvelous city are secrets, riddles each one more perplexing than the last. You and your fellow wanderers must race to uncover the hidden artifacts, each piece a key to your ultimate freedom.

You must heed the riddles scattered across the land, for they will guide you from one artifact to the next. But beware! Only the swiftest shall succeed. Collect all the artifacts, uncover the secret passphrase, and the gates of Solstara will open to you—if you are the first.

But fear not, should you falter. The city's guardian whispers riddles to those who seek guidance, and she is ready to offer assistance. Use your wits, explore the ancient city, show your cunning and __ESCAPE SOLSTARA__.
## Links 🔗 <a name="links">
**Link To Build Folder:** https://drive.google.com/drive/folders/1cA3443J4xZ-ED0Oge7mBRLtq1yLPYdjz?usp=drive_link 

**Link To Project:** https://github.com/Langton49/ES_project

## How I Made It 🔨 <a name="how-i-made-it">

### Technology Stack <a name="tech-stack">
- Unity Editor (Version 2022.3.28f)
- Microsoft Visual Studio (Version 17.9.6)
- Microsoft .NET Framework (Version 4.8.09037)
- C# (version 7.3)
- Amazon Q Developer
- AWS GameLift
- AWS Lambda
- AWS Cognito
- ChatGPT API

### Features <a name="features">
#### Goal <a name="goal">
I participated in the AWS Game Builder Challenge, where the goal was to build a game using AWS services. As a beginner with AWS, I initially struggled with deciding what to create. After coming up with 5 ideas, I eventually chose Escape Solstara as the winning idea. 

I wanted to create a multiplayer game that was as competitive and exhilirating as many other popular multiplayer games-Fortnite for example-but with more of a brain-teasing element. The result is Escape Solstara, a scavenger hunt game set in a medieval city, where players must decipher riddles and uncover hidden artifacts to escape.

#### Dynamic Riddle Generation <a name="dynamic-riddle-gen">

To ensure that each game session felt fresh and unpredictable, I wanted the riddles to be dynamically generated rather than prewritten. Manually writing riddles for hundreds of possible artifacts (objects the player must find to reveal the next clue) would have been both time-consuming and limiting, so I went with the next best thing that's capable of generating content quickly, generative AI. 

I used ChatGPT-4o to generate riddles based on the name of the artifact and its location in the city. In the system prompt, I added descriptions for each area of the city, allowing the model to generate more clever riddles for the player to solve. 

The artifacts are assigned at random for each player, in each game session. When all players have entered the lobby the artifacts are loaded and ChatGPT generates riddles for each one.

#### The Guardian <a name="guardian">


To keep the game engaging, I designed the riddles to be easy to follow by keeping their format simple in the system prompt. However, since there’s no time limit, I had to consider a case where all the players might get stuck on their respective clues, potentially causing the game to stall indefinitely.

To address this, I implemented The Guardian, a chatbot-style assistant powered by ChatGPT-4o that helps players solve their riddles. The Guardian has access to key information, including:

- The artifact the player is searching for.
- The location where it can be found.
- The preset passphrase needed to escape.

However, to maintain a challenge, a player can only ask YES or NO questions related to this information. This ensures they receive guidance without making the game too easy.

#### Multiplayer <a name="multiplayer">

The multiplayer functionality was definitely the most challenging part of this project. This was not only the first fully functional game I've made, but it also had to support multiplayer gameplay. I was not prepared the difficulty of this feature but despite my limited experience, I tackled the challenge head-on and implemented it as best as I could.

The multiplayer functionality is made possible by 3 AWS services:

- Amazon GameLift – Handles game session management and real-time communication
- AWS Lambda – Manages matchmaking and session management
- Amazon Cognito – Provides guest access authentication

When the player creates or joins a game, a function is called to connect them to the GameLift server. On the server side: 

1. The game connects to Cognito, creating a Cognito identity to allow guest access.
2. Once authenticated, an AWS Lambda function is triggered to handle matchmaking and session management through GameLift’s API.
3. GameLift’s server script manages real-time communication and game logic for all connected player sessions.

While setting up the server-side logic was relatively straightforward, my biggest challenge was translating real-time multiplayer data into smooth on-screen gameplay. Since I initially developed the entire game as an offline single-player experience, I ran into issues where scripts couldn't correctly differentiate between local and remote player prefabs. Debugging the data synchronization between players was arduous, but I eventually figured out an efficient way to send and translate remote player data, making multiplayer functionality possible. 

## How To Play 🎮<a name="how-to-use">
### Install <a name="install">
- Navigate to the Google Drive link located under [Links](#links)
- Download the build folder through the link above.
- Find the Escape Solstara zip folder and unzip it.
- Move the Escape Solstara.exe file to the parent folder (the one containing UnityPlayer.dll).
- Launch the Escape Solstara.exe file.
### In-Game <a name="in-game">
- Enter the desired number of players and specify how many artifacts each player must find before revealing the passphrase.
- The game will wait for all players to join before presenting the first riddle and allowing you to speak with the guardian.
- Each riddle leads to an artifact hidden within the city.
- Explore the city to find the artifact, which will be marked by a glowing green arrow when you’re nearby.
- Once all required artifacts are collected, the passphrase will be revealed.
- Approach any statue in the city and enter the passphrase.
- If correct, you’ll gain the ability to approach a city gate and escape.
- Each player has access to a chatbot for assistance with riddles or deciphering the passphrase without collecting all artifacts.

## Contributing 🤝<a name="contributing">
Because software development is an ongoing and collaborative process, contributions are welcome. Simply create a branch, commit your changes, push to the branch and open a pull request.

## Credits 👍 <a name="credits">
- [SpaderDaBomb](https://www.youtube.com/@spaderdabomb): Comprehensive tutorial on 3rd person character controllers.
- [Alexandre Bruffa](https://www.youtube.com/@alexandrebruffa): Explanation of how AWS Gamelift works.
- [Tidal Flask Studios](https://www.tidalflask.com/): Provided an immersive sample scene with beautiful city setting from asset store.
- [Blink Studios](https://blinkstudios.dev/): 3D character game object from asset store.

## Contact ✉<a name="contact">
__Author:__ Munashe Mukweya\
__Email:__ munashemukweya2022@gmail.com\
__GitHub:__ https://github.com/Langton49


