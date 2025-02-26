# [End-to-End Navigation with Branch Turning Support Using Convolutional Neural Network](https://www.semanticscholar.org/paper/End-to-End-Navigation-with-Branch-Turning-Support-Seiya-Carballo/b9db6c16504dd3e37fb4d47f140174ef80e7a04e)
*by S. Seiya, A. Carballo, E. Takeuchi, C. Miyajima, and K. Takeda*

##### Introduction
- development of a navigation system based on end-to-end learning
    - follow assigned trajectories (incl. turning at intersections)
- split into 2 tasks:
    - branch detection
    - behavior change to reach different destination

##### End-to-End Navigation Along a Specified Route
- model needs to be able to detect intersections in order to follow
 a route
- trained along a certain path (model A: right-right;
 model B: right-left)
    - different model for each trajectory needed

##### Navigating Intersections Using Target Direction
- single model approach by frontal camera + target (waypoint)
    - expected to be applicable to unknown trajectories
- introduced vector to next target after convolution layers
- Loss function:
    - root mean square error (RMSE) between estimated result and
     supervised signal
    - L2 norm (euclidean distance from origin)
    - difference between estimated and supervised steering value
- pure pursuit algorithm to train robot to return back to center of
 trajectory upon deviation
- model needs target direction vector (2D)
    - generated by navigation system (e.g. GPS)
    - model-based driving system

##### Results
- robot capable to follow different trajectories according to
 changes in targeting directions
    - even following unknown routes containing a variety of
     trajectories and several branches
- model does not correspond exactly to target direction, instead
 model learned how to navigate locally
