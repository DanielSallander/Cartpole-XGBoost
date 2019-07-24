# Cartpole using XGBoost
This implementation of OpenAI Gym Cartpole environment utilizes the XGBoost library for creating predictions of future states at any given state, and from there choose the best action using a custom reward function.

The Cartpole environment consists of 4 features for any given state. In this implementation 4 XGBRegressor models are used - one for each state feature. The training data consists of state-action pairs and each model is fit using the training data with one timestep offset, so for a given model current state feature is predicted by previous state-action. 

The outcome varies but the environment is most commonly solved after approximately 10 episodes.
In the jupyter notebook in the repository the environment is solved after 7 episodes.


