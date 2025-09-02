# Training a Regression Deep Neural Network to predict Closing Prices of Crude Oil

## 💻 Setup Guide
1. Clone the repository to a local directory
    - In a terminal enter the following command:
    - ```git clone https://github.com/CongaJAMM/Liquid-Gold.git```

2. Create a [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/) environment using the './setup/requirements.yaml' file
    - ```conda env create -f dev_requirements.yaml```
    - Activate the environment 
    - ```conda activate WP_env```

3. Run the training script with the different training script parameters and configurations '[configs/config.json](configs/config.json)'

<details>
  <summary><h2>⚙️ Training Script Argparse Parameters</h2></summary>

- `--epochs`  
  - **Type**: `int`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value. 
  - **Description**: Number of training epochs to run.

- `--learning_rate`  
  - **Type**: `float`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value. 
  - **Description**: Learning rate used by the optimizer.

- `--max_grad_norm`  
  - **Type**: `float`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.
  - **Description**: The Maximum L2 Norm of the gradients for Gradient Clipping.

- `--dataloader_batch_size`  
  - **Type**: `int`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.  
  - **Description**: Batch size used by the dataloaders for training, validation, and testing.

- `--dataloader_pin_memory`  
  - **Type**: `bool`  
  - **Default**: False
  - **Description**: Use flag to enable pinned memory in dataloaders (enabled by default).

- `--dataloader_num_workers`  
  - **Type**: `int`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.  
  - **Description**: Number of subprocesses to use for data loading.

- `--log_iterations`  
  - **Type**: `int`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.  
  - **Description**: Frequency (in iterations) to log training progress.

- `--eval_iterations`  
  - **Type**: `int`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.  
  - **Description**: Frequency (in iterations) to evaluate the model.

- `--use_cuda`  
  - **Type**: `bool`  
  - **Default**: False  
  - **Description**: Use flag to enable CUDA for training if available.

- `--device`  
  - **Type**: `str`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value.  
  - **Description**: Device to use for training (e.g., `"cpu"`, `"cuda:0"`). Overrides `--use_cuda`.

- `--save_model`  
  - **Type**: `bool`  
  - **Default**: False
  - **Description**: Use flag to save the trained model after training.

- `--model_output_path`  
  - **Type**: `str`  
  - **Default**: See '[/configs/README.md](/configs/README.md)' for default value. 
  - **Description**: File path to save the trained model.

</details>

---

### Example Commands:
- ```python model_training.py```
    - Uses the default settings to run the script.
    
- ```python model_training.py --epochs=32  --log_iterations=4 --eval_iterations=8 --save_model```
    - Explanation: Run for 32 epochs and log the Batch Loss every 4 iterations. Evaluate the Policy-under-training every 8 epochs. Lastly, save the trained model (uses the default save path.) Uses default for everything else.
    
    
- ```python model_training.py --epochs=32  --use_cuda --save_model --model_output_path=models/first-trained-model.pt```
    - Explanation: Let the system detect if your system has GPU capabilities and has cuda available for training. During the training setup, the system dynamically sets the device variable for model training. Saves the trained model using the specified location. Uses default for everything else.

---

## For detailed config file options, see '[/configs/config.json](/configs/config.json)' and '[/configs/README.md](/configs/README.md)'.