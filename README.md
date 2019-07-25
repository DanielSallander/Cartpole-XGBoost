# Cartpole using XGBoost
This implementation of OpenAI Gym Cartpole environment utilizes the XGBoost library for creating predictions of future states at any given state, and from there choose the best action using a custom reward function.

The states in the Cartpole environment consists of 4 features. The purpose of using the XGBoost library is to predict future states given current state so in this implementation 4 XGBRegressor models are used to separately predict one state feature each - the combination of these predictions therefore constitutes the predicted state. The training data consists of state-action pairs and each model is fit using the training data with one timestep offset, so for a given model current state feature is predicted by previous state-action. 

The predicted states are organized in a tree-like structure where each level is defined by +1 timestep into the future. 
This enables predictions to be made at given timesteps into the future.
The reward function is evaluated for states in the last tree level. Actions are then selected by traversing the tree back to the current state from the state with the best reward. 

In some cases the environment is solved after 1 episode and in some other extreme cases the environment is solved after 100+ episodes.
So the outcome varies but the environment is most commonly solved after approximately 10 episodes.
In the jupyter notebook in the repository the environment is solved after 7 episodes.


