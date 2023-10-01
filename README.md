# Object Importance Estimation Using Counterfactual Reasoning


**News**: \
**28.09.2023:** We released the code to generate the counterfactual trajectories. \
**22.09.2023:** We released the code to reproduce the results in the paper, [here](https://github.com/vehicle-importance/oiecr).


## [Project Page](http://vehicle-importance.github.io) | [Paper (Coming Soon)]() 

This repository provides code for the following paper:

- [Pranay Gupta](https://pranaygupta36.github.io), [Abhijat Biswas](https://www.cs.cmu.edu/~abhijatb/), [Henny Admoni](https://hennyadmoni.com/), [David Held](https://davheld.github.io/), Vehicle Importance Estimation using Counterfactual Reasoning, *Under Submission*  

<!-- ![demo]() -->

# Content
* [Setup](#setup)
* [Download Simulation Recordings](#download-simulation-recordings)
* [Generating True and Counterfactual Trajectories](#generating-true-and-counterfactual-trajectories)
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

```

Setup LAV adapted for Counterfactual Reasoning from [here](https://github.com/pranaygupta36/LAV)

## Download Simulation Recordings 

1. Download the HOIST dataset using the instructions given [here](https://github.com/vehicle-importance/oiecr#Download-HOIST-Dataset).
2. The `recordings` directory contains the CARLA simulation recording of the 6 routes.


## Generating True and Counterfactual Trajectories

Start the Carla Server

``` bash
./<path_to_carla>/CarlaUE4.sh

```

To generate the conterfactual trajectories and extract the sensor data run:

``` bash
python start_replaying.py -f ./recordings/RouteScenario_<route_id>_rep0.log --route-id <route_id>

``` 

The data would be recorded in `./saved_data`. The directory structure of saved_data is as follows:

```
saved_data
└── 2
    ├── data
    │   ├── 1.npy
    │   ├── 2.npy
    │   .
    │   .
    ├── og
    │   ├── bev
    │   │   ├── 1.png
    │   │   ├── 2.png
    │   │   .
    │   │   .
    │   ├── bev_unmarked
    │   │   ├── 1.png
    │   │   ├── 2.png
    └── recording_data
        ├── bev_projected
        │   ├── projected_1.png
        │   ├── projected_2.png
        │   .
        │   .
        └── data
            ├── 1.npy
            ├── 2.npy
            .
            .
├── 9
.
.
└── 31
```

2, 9, 14, 19, 24, 31 are route-ids for the selected routes from the longest6 benchmark. The `./saved_data/data` directory contains the counterfactual trajectory generated after removing the objects in the scene.

The `./saved_data/og` directory contains the unmarked bev images in the `./saved_data/og/bev_unmarked` directory and the annotated frames with counterfactual trajectories in the `./saved_data/og/bev` directory.

The `./saved_data/recording_data/bev_projected` directory contains the annotated frames with counterfactual trajectories for the velocity perturbation scores where the trajectories are forecast using a constant velocity model.

The `./saved_data/recording_data/data` directory contains the perturbed and unperturbed vehicle trajectories forecast using a constant velocity model.

## Evaluation

For evaluation refer this [repository](https://github.com/vehicle-importance/oiecr).

## Citation (Coming Soon)
