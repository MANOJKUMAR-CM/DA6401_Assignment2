# DA6401_Assignment2
This repository contains files for Assignment 2 of the course DA6401 - Introduction to Deep Learning at IIT Madras.

## Assignment Overview  
### Objective:
- Part A: To build and train a CNN model from scratch
- Part B: To fine tune a pre trained Model

## Links:

## [Wandb Report](https://wandb.ai/manoj_da24s018-iit-madras/CNN-inaturalist_12K-HyperParameterSweep-Trail1/reports/DA6401-Assignment-2--VmlldzoxMjE5MTYyMA?accessToken=j8kzktlay7gghy82kkeoqmq3dsew8olvvo0cktec9ah0z3xk39bvayy8837tzz5p)

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

  ```

To Train the model on the best hyperparameters obtained from the sweeps:
- Run `PartA/DL-Assignment2-Task1.ipynb`, It would train the model, predict on test set and save a `.png` file which would contain the model's prediction on a random set of 30 samples from test set.
  
#### Update WandB Credentials  
Before running the sweep, update the following command with your own WandB credentials:  

```python
wandb.sweep(sweep_config, entity="<your_name>", project="<your_project_name>")
```

### Part B
To fine tune a pre trained model (Eg: VGG16) on a subset of `iNaturalist dataset`
- Run `PartB/DL-Assignmnet2-Task2.ipynb`

These jupyter files expect the Dataset to be present in the same directory: 

```python
Directory Structure:
- inaturalist_12K/train
- inaturalist_12K/test
- DL-Assignmnet2-Task2.ipynb
- DL-Assignment2-Task1.ipynb
- DL-Assignment2-Task1-HyperParameterSweep.ipynb
```
