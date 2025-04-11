# DA6401_Assignment2
This repository contains files for Assignment 2 of the course DA6401 - Introduction to Deep Learning at IIT Madras.

## Assignment Overview  
### Objective:
- Part A: To build and train a CNN model from scratch
- Part B: To fine tune a pre trained Model

## Links:

## [Wandb Report](To be completed)

## [Github: Assignment2 - DA6401](https://github.com/MANOJKUMAR-CM/DA6401_Assignment2)

### Part A
To perform the hyper parameter sweep on the CNN model:
- Run `PartA/DL-Assignment2-Task1-HyperParameterSweep.ipynb`, make sure to update `wandb.sweep()` with your own wandb credentials before running.
- **Hyperparameter Sweeps Configuration:**
  ``` python
  sweep_config = {
    "name": "CNN - HyperParameter Search",
    "metric": {"name": "val_accuracy", 
            "goal": "maximize"},
    "method": "random",
    "parameters": {
        "learning_rate": {
            "values": [0.001, 0.005, 0.01]
            },
        "num_conv_layer": {
            "values": [3, 5, 7]
            },
        "num_conv_filter": {
            "values": [16, 32]
            },
        "filter_org":{
            "values": [0.5, 1, 2]
        },
        "batch_norm": {
            "values": [True, False]
            },
        "dropout": {
            "values": [0.0, 0.2, 0.3, 0.4]
            },
        "num_dense_layers": {
            "values": [1, 2]
            },
        "dense_neurons": {
            "values": [256, 512]
            },
        "kernel_size":{
            "values":[3, 5]
        },
        "activation_func":{
            "values": ["relu", "gelu", "silu", "mish", "tanh"]
        }
    }
}
  ```

