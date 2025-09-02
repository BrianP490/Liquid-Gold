# 🗂️ Configuration File Documentation

This document describes the parameters available in the `/configs/config.json` file.


<summary><h2>Data</h2></summary>

Covers the essential data configurations for the Data Pipeline

- `dataset_url`  
  - **Type**: `str`  
  - **Default**: `hf://datasets/MaxPrestige/CRUDE_OIL_PRICES/Data/OIL_DATASET.csv`  
  - **Description**: URL to the dataset hosted on Hugging Face.

- `root_data_dir`  
  - **Type**: `str`  
  - **Default**: `./Data`  
  - **Description**: Root directory where data files are stored.

- `data_file_path`  
  - **Type**: `str`  
  - **Default**: `OIL_DATASET.csv`  
  - **Description**: Filename of the dataset.

- `data_splits_dir`  
  - **Type**: `str`  
  - **Default**: `DataSplits`  
  - **Description**: Directory containing train/val/test splits.

- `scaler_dir`  
  - **Type**: `str`  
  - **Default**: `Scalers`  
  - **Description**: Directory to save/load data scalers.

- `target_column`  
  - **Type**: `str`  
  - **Default**: `Close`  
  - **Description**: Column name to be predicted.

- `extra_dropped_columns`  
  - **Type**: `list`  
  - **Default**: `["Date"]`  
  - **Description**: List of columns to drop from the dataset.


<summary><h2>Argparse Parser Defaults</h2></summary>

Used to provide the argparse parser default values and attributes.

- `epochs`  
  - **Type**: `int`  
  - **Default**: `8`  
  - **Description**: Number of training epochs to run.

- `learning_rate`  
  - **Type**: `float`  
  - **Default**: `0.0003`  
  - **Description**: Learning rate used by the optimizer.

- `max_grad_norm`  
  - **Type**: `float`  
  - **Default**: `3.0`  
  - **Description**: Maximum L2 norm for gradient clipping.

- `dataloader_batch_size`  
  - **Type**: `int`  
  - **Default**: `64`  
  - **Description**: Batch size for training and evaluation.

- `dataloader_pin_memory`  
  - **Info**: Use flag to Enable pinned memory in dataloaders. See 'Simulated Args' section for more information on ipynb tesing.

- `dataloader_num_workers`  
  - **Type**: `int`  
  - **Default**: `0`  
  - **Description**: Number of subprocesses for data loading.

- `log_iterations`  
  - **Type**: `int`  
  - **Default**: `32`  
  - **Description**: Frequency of logging training progress.

- `eval_iterations` 
  - **Type**: `int`  
  - **Default**: `32`  
  - **Description**: Frequency of model evaluation.

- `use_cuda`
  - **Info**: Use flag to Enable CUDA for training if available. See 'Simulated Args' section for more information on ipynb tesing.

- `device`
  - **Type**: `str`  
  - **Default**: `cpu`  
  - **Description**: Device to use for training (e.g., 'cpu', 'cuda:0').

- `save_model`  
  - **Info**: Use flag to save the trained model after training. See 'Simulated Args' section for more information on ipynb tesing.

- `model_output_path`
  - **Type**: `str`
  - **Default**: `./models/liquid_gold_model.pt`  
  - **Description**: Path to save the trained model.


<summary><h2>Model</h2></summary>

For the model architecture, such as the number of repeating model blocks.

- `in_dim`  
  - **Type**: `int`  
  - **Default**: `22`  
  - **Description**: Input dimension size.

- `intermediate_dim`  
  - **Type**: `int`  
  - **Default**: `128`  
  - **Description**: Size of intermediate hidden layers.

- `out_dim`  
  - **Type**: `int`  
  - **Default**: `1`  
  - **Description**: Output dimension size.

- `num_blocks`  
  - **Type**: `int`  
  - **Default**: `12`  
  - **Description**: Number of model blocks used.

- `dropout_rate`  
  - **Type**: `float`  
  - **Default**: `0.1`  
  - **Description**: Dropout rate for regularization.


<summary><h2>Logging</h2></summary>

Used to configure the error/info logging behaviors.

- `log_to_file`  
  - **Type**: `bool`  
  - **Default**: `True`  
  - **Description**: Enable logging to a file.

- `log_file`  
  - **Type**: `str`  
  - **Default**: `logs/app.log`  
  - **Description**: Path to the log file.

- `logger_name`  
  - **Type**: `str`  
  - **Default**: `main`  
  - **Description**: Name of the logger instance.

- `log_level`  
  - **Type**: `str`  
  - **Default**: `INFO`  
  - **Description**: Logging level (e.g., INFO, DEBUG).

- `log_mode`  
  - **Type**: `str`  
  - **Default**: `w`  
  - **Description**: File mode for logging (e.g., 'w' for overwrite, 'a' for appending).

- `log_to_console`  
  - **Type**: `bool`  
  - **Default**: `True`  
  - **Description**: Enable logging to the console.


<details>
  <summary><h2>Simulated Args</h2></summary>

Required for ipynb testing, due to the argparser incompatability.

- `--epochs`  
  - **Type**: `str`  
  - **Default**: `1`  
  - **Description**: Override number of epochs for simulation.

- `--learning_rate`  
  - **Type**: `str`  
  - **Default**: `0.003`  
  - **Description**: Override learning rate for simulation.

- `--log_iterations`  
  - **Type**: `str`  
  - **Default**: `256`  
  - **Description**: Override log frequency for simulation.

- `--eval_iterations`  
  - **Type**: `str`  
  - **Default**: `64`  
  - **Description**: Override evaluation frequency for simulation.

- `--dataloader_pin_memory`  
  - **Type**: `bool`  
  - **Default**: `false`  
  - **Description**: Override dataloader pin memory behavior.

- `--use_cuda`  
  - **Type**: `bool`  
  - **Default**: `false`  
  - **Description**: Override cuda behavior.

- `--save_model`  
  - **Type**: `bool`  
  - **Default**: `false`  
  - **Description**: Override model saving behavior.

- `--model_output_path`  
  - **Type**: `str`  
  - **Default**: `./models/liquid_gold_model.pt`
  - **Description**: Override model output path.

</details>
