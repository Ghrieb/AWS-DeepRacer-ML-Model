def reward_function(params):
    """
    Example of rewarding the agent to follow the center line.
    """

    # Initialize reward
    reward = 1e-3  # Default small reward to discourage going off track

    # Read input parameters
    track_width = params['track_width']
    distance_from_center = params['distance_from_center']
    steering_angle = params['steering_angle']
    speed = params['speed']

    # Calculate 3 markers that are at varying distances away from the center line
    marker_1 = 0.1 * track_width
    marker_2 = 0.25 * track_width
    marker_3 = 0.5 * track_width

    # Give higher reward if the car is closer to the center line
    if distance_from_center <= marker_1:
        reward += 2.0
    elif distance_from_center <= marker_2:
        reward += 0.5
    elif distance_from_center <= marker_3:
        reward += 0.1  # getting close to off track

    # Incentivize going fast on straightways and slower on curves
    if -5 < steering_angle < 5:
        # If on a straight path, reward higher speed
        if speed > 2.5:
            reward += 2.0
        elif speed > 2.0:
            reward += 1.0
    elif steering_angle < -15 or steering_angle > 15:
        # If on a sharp turn, reward slower speed
        if speed < 1.8:
            reward += 1.0
        elif speed < 2.2:
            reward += 0.5

    return float(reward)
