# Player Neural Agents

The soccer players these days have grown into something larger. Their personalities and their skills dominate the game. EA's FIFA game series is the best soccer game to be played out there, but it is not the best soccer game. When we play against CPU (not calling it CPU AI), we are playing against a bot which is not dissimilar with other bots of other teams. Sure there are some changes made when we switch the CPU from Real Madrid to Liverpool, but it doesn't feel like I am playing against a Real Madrid or a Liverpool. There is no personalization.

When I play Career Mode with a player, the decisions and the actions of the club are handled by the CPU and it's a mess. For example, I played as Vini Jr in career mode. In the first season itself (2022/23), Real Madrid signed Gabriel Jesus, Enzo Fernandez, Trent Alexander Arnold and sold Eder Militao, Antonio Rudiger and Tchouameni. Such decision reflect the absurdity and the randonmess with which the AI takes decision. 

EA have done a good jon with their FIFA game series so far, but the next logical step is to integrate Neural Networks in the game, which will help personalize the whole experience of the game and make you feel like you are actually up against a Real Madrid AI not some generic CPU.

So I propose a neural network solution called Player Neural Agent. 

A Player Neural Agent is a neural network which ingests attributes of a player's physicality and movement to then predict the next action. This may be achieved by 

(1) Obtaining a minute's footage of a player in motion

(2) Create a batch of frames from the video of the player, eg. 1 frame/second

(3) Creating an algorithm which can generate features based off of the frames. Features like :

   (a) Relative position of elbow to the shoulder
	
   (b) Relative position of the elbow to the center of upper body

   (c) Relative position of the knee to the groin region

   (d) Relative position of the knee to the ankle

(4) After we are able to generate such and many more features for each frame, we need to build markov chains over a specific time window (10 seconds, 20 seconds) so that we are able to capture the transition of posture and body language triggered by an event. For example, player A is dribblng with the ball and he suddenly slows down the ball with the sole plate of his cleats (change in posture and body language) because an opposition player is stepping upto him (event).

(5) Our target is to learn how a player moves his/her body when responding to change in the game state.

Given a set of attributes describing the posture, structure and body language of a player and the presence of stimuli at time t, a Player Neural Agent must be able to predict the set of attributes describing the posture, structure and body language of a player at time t+1.

For (3), we should investigate into open source solutions. Research into this will be essential.   

# Other Avenues

We can also build out neural networks which can handle decisioning done when the club actions are in CPU mode. Referencing the player career mode example, we can build a neural network trained on real world transfers done by a club to nake sure the transfer patterns feel like that of the club in question. 

Ambitious goal is to have an infrastructure which can contain multiple neural networks and handle the communication between them so that we can achieve this in real time. That way, we may end up with a better football game. This architecture and AI can also be applied to other games to make them better.
