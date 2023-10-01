# Object Importance Estimation Using Counterfactual Reasoning


**News**: \
**28.09.2023:** We released the code to generate the counterfactual trajectories.
**22.09.2023:** We released the code to reproduce the results in the paper, [here](https://github.com/vehicle-importance/oiecr).


## [Project Page](http://vehicle-importance.github.io) | [Paper (Coming Soon)]() 

This repository provides code for the following paper:

- [Pranay Gupta](https://pranaygupta36.github.io), [Abhijat Biswas](https://www.cs.cmu.edu/~abhijatb/), [Henny Admoni](https://hennyadmoni.com/), [David Held](https://davheld.github.io/), Vehicle Importance Estimation using Counterfactual Reasoning, *Under Submission*  

<!-- ![demo]() -->

# Content
* [Setup](#setup)
* [Download Simulation Recordings](#download-simulation-recordings)
* [Generating True and Counterfactual Trajectories](#generating-true-and-counterfactual-trajectories-coming-soon)
* [Citation *(Coming Soon)*]()



## Setup

First, you have to install carla. (*The installation script has been taken from [PlanT](https://github.com/autonomousvision/plant)*)

``` bash
# 1. Clone this repository
git clone https://github.com/vehicle-importance/generating_counterfactual_trajectories.git
cd generating_counterfactual_trajectories

# 2. Setup Carla
chmod +x setup_carla.sh
./setup_carla.sh

# 3. Setup LAV adapted for Counterfactual Reasoning. 
Refer [here](https://github.com/pranaygupta36/LAV)
```


## Download Simulation Recordings 

1. Download the HOIST dataset using the instructions given [here](https://github.com/vehicle-importance/oiecr#Download-HOIST-Dataset).
2. The `recordings` directory contains the CARLA simulation recording of the 6 routes.


## Generating True and Counterfactual Trajectories

## Citation (Coming Soon)
