


### Before you begin
Before you begin, make sure you have satisfisfied the prerequisites to use Weights and Biases. For more information, see [add new link].



### Set up your Python training script
Add awesome, high-level overview of how to set up training script.

1. Import the Weights and Biases library
```python
import wandb
```
2. Create the hyperparameter values to `wandb.init` to populate `wandb.config`.
```python 
import config  # python file with default hyperparameters

# Set up your default hyperparameters
hyperparameters = config.config

# Pass them wandb.init
wandb.init(config=hyperparameters)

# Access all hyperparameter values through wandb.config
config = wandb.config

# Set up your model
model = make_model(config)
```
3. Set up your model. Pass the values in your configuration:
```python
# Set up your model
model = make_model(config)
```
4. Log metrics to see them in the live dashboard.
```python
# Log metrics inside your training loop
for epoch in range(config["epochs"]):
    val_acc, val_loss = model.fit()
    metrics = {"validation_accuracy": val_acc,
               "validation_loss": val_loss}
    wandb.log(metrics)
```

For more information, see the Weights & Biases [API Reference Guide](https://docs.wandb.ai/ref/python).

