# AWS DeepRacer Model: Achieving Top Race Times with Reinforcement Learning

Welcome to my AWS DeepRacer repository! This project showcases my journey to the top 3 in my country's AWS DeepRacer competition. By training and refining a deep reinforcement learning (RL) model, I achieved a qualifying time of under 2 minutes on the virtual track, prequalifying for the AWS AI & ML scholarship. This repository contains all the necessary resources, visualizations, code, and insights that led to this achievement.
![image](https://github.com/user-attachments/assets/eec5b83d-8e1c-4dcc-a2b3-02eb0ba07cd6)

## Table of Contents
- [Overview](#overview)
- [Model Architecture](#model-architecture)
- [Reward Function](#reward-function)
- [Visualization](#visualization)
  - [Track Waypoint Map](#track-waypoint-map)
  - [Reward Function Diagram](#reward-function-diagram)
- [Contributing](#contributing)
- [License](#license)

---

## Overview
This project focuses on creating a competitive AWS DeepRacer model using reinforcement learning. The core idea is to optimize a reward function that encourages the car to complete the track as efficiently and quickly as possible while maintaining stability.

My model achieved a **qualifying time under 2 minutes**, placing me in the **Top 3 in my country**. This result prequalified me for the **AWS AI & ML Scholarship**.

https://github.com/user-attachments/assets/fb54fcc5-2784-407f-8933-cd211ab62133

---

## Model Architecture
The model is trained using AWS's SageMaker, It's based on a convolutional neural network that processes the car's camera feed, while a reinforcement learning agent maps these images to actions that control the car's throttle and steering.

![image](https://github.com/user-attachments/assets/6427f750-a70f-46b3-a51c-98d969db1a0a)




The `.pb` model file can be found in the `/models/` directory.

---

## Reward Function
The reward function is the heart of the DeepRacer model. It guides the model's decisions during training by rewarding behaviors that lead to completing the track faster.

### Code Snippet
Here's the core logic of the reward function:

```python
def reward_function(params):
    # Example of rewarding the agent to follow center line

    # Read input parameters
    track_width = params['track_width']
    distance_from_center = params['distance_from_center']

    # Calculate 3 markers that are at varying distances away from the center line
    marker_1 = 0.1 * track_width
    marker_2 = 0.25 * track_width
    marker_3 = 0.5 * track_width
```


## Contributing
Feel free to fork this repository and make your own improvements. If you have suggestions or encounter issues, please submit a pull request or open an issue.

## License
This project is licensed under the MIT License. See the LICENSE file for more information.
