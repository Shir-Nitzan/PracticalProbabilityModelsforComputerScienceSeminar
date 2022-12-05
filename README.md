# PracticalProbabilityModelsforComputerScienceSeminar
We are gonna predict the matches in the world cup till the big final. We are assuming that the number of goals occurring in a game is described by the Poisson distribution. 

We got the data about the average goals rate of each team during all past world cups.  

![image](https://user-images.githubusercontent.com/62726511/205758207-be29e403-c253-4460-b88a-90bc7f22c537.png)

## Poisson Distribution

We investigated the distribution of goals scored by the team.
For example the PMF of Belgium Poisson distribution is where the goal rate is  λ=1.417 goals per game.

<img src="https://user-images.githubusercontent.com/62726511/205758458-63ef5b61-6cc9-4242-b3b9-3d2f6b471885.png" width="423" height="81">

where k is a natural natural number.

![image](https://user-images.githubusercontent.com/62726511/205758494-121e1cf5-d797-4c88-a378-1b9c16ca6db2.png )

## The Exponential  Distribution


We will check what is the probability of seeing a specific interval between goals.
Let’s see the cdf of the distribution of time between goals by Brazil.
Brazil has rate of λ=0.023 goals per minute, X is the time between goals.

![image](https://user-images.githubusercontent.com/62726511/205760068-fb68d115-3134-41e8-baef-0c3e6e7aad3a.png)
![image](https://user-images.githubusercontent.com/62726511/205760159-fb2dc62e-f2c3-431f-8e17-743c8764265b.png)

## Prediction using the Poisson distribution

For the knockouts, we don’t need to predict the points, but the winner of each bracket. This function calculates the probability to win for each team. To do so, we calculated lambda for each team using the formula average_goals_scored * average_goals_conceded.

Then we simulated all the possible scores of a match from 0–0 to 10–10 but without draws. In knockout there are no draws (kind of), and possibility of a tie didn't help the final calculation, so we removed it.

Once we have lambda and x, we use the formula of the Poisson distribution to calculate p.

After each round, we update the winners using the predict_winner function and then update the next round with the new games.

![image](https://user-images.githubusercontent.com/62726511/205760238-abf1ae00-db23-4a17-9938-3b42c154ae5e.png)

So after we predicted all the stages, we finally got the winners.

And the winners are:

![image](https://user-images.githubusercontent.com/62726511/205760422-60344d00-f696-4949-8e07-707f8cfe7fae.png)
