# Cartpole using XGBoost
This implementation of OpenAI Gym Cartpole environment utilizes a set of models from the XGBoost library, organized in two layers.

The purpose of the first layer is to predict future states given current state, so four XGBRegressor models are used to separately predict one state feature each. The combination of these predictions therefore constitutes the predicted state. The training data consists of state-action pairs and each model is fit using the training data with one timestep offset, so for a given model current state feature is predicted by previous state-action. Actions are selected using a a custom reward function.

The second layer consists of an XGBClassifier which uses data from successful episodes to learn which actions to take in given states.

In the jupyter notebook in the repository the environment is solved on average after 3.1 episodes in 10 separate runs.


