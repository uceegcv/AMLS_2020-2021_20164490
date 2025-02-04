# README
# AMLS_2020-2021_20164490
This code contains the scripts to train four models for differernt image recognition tasks. Tasks A1 and A2 involve determining the gender and smiling status of real celebrity images, and B1 and B2 aim to determine the face shape and eye colour of cartoon avatar aimages. Pre-trained models are intended to be saved in the folder for each task to allow main.py to run. These are provided as files able to download from Google Drive. The outputs of main.py are the testing accuracies of these pre-trained models on an unseen dataset that is pasted into the user's local folder under 'Datasets'.

# Classes

- class Data_loader(Dataset):
    - Constructors: Dataset (Pytorch)
    - Methods:
        - _init_:
        creates dataframe
        sets up image directory
        adds image transformations
        reads in filenames
        reads label file
        - _len_:
        returns length of dataframe
        - _getitem_:
        opens image
        adds transformations
        assigns label
        
- class ImAugtransforms:
    - Methods:
        - _init_:
        adds image transformations using imgaug iaa 
        - _call_:
        image as numpy array
        
        
# Functions 

- def get_num_correct:
    - sums the number of correct predictions
    
- def train(model,
          criterion,
          optimizer,
          train_loader,
          valid_loader,
          save_file_name,
          scheduler,
          max_epochs_stop=5max_epochs_stop,
          n_epochs=epochs,
          print_every=1,
          ):
    - begins trains model with model.train
    - prints training and validation accuracy and loss
    - updates weights for next epoch with model.eval
    - iterates through specified number of epochs

- def crossvalid(model=None, criterion=None, optimizer=None, dataset=None, k_fold=5):
    - k-fold cross-validation analysis

# Instructions for use

- The code main.py will run on any Python platform

- To enable running of main.py, the saved models for each task must be downloaded and added to the folder for the corresponding task:
    
    - Expected extensions are .pth
    
    - A1 Model download folder, requires saving in A1 folder
    https://drive.google.com/file/d/1-3AU2etnp2I5Fr9D_eicAC_pd1a8G8IH/view?usp=sharing
    
    - A2 Model download folder, requires saving in A2 folder
    https://drive.google.com/file/d/1WBLQQFWvOyhIk1EY5bhzX9CRab7uh4KK/view?usp=sharing
    
    - B1 Model download folder, requires saving in B1 folder
    https://drive.google.com/file/d/13oD68J29etXjisbRA5D-X1h3bbK60wZ7/view?usp=sharing
    
    - B2 Model download folder, requires saving in B2 folder
    https://drive.google.com/file/d/13QNY7ZXG1pkdTunALnx3_Eu1KqCo8BNE/view?usp=sharing
    
- The path to this code folder must be specified at the start of main.py to enable it to run

- For each task, a user input of Y/N is required.
    - There will be a prompt ("Do you want to print predictions for each image in test set? (Y/N)")
    - If select no (N), there will be no print-outs of individual predictions
    - If select yes (Y), the predictions for each individual test image will be shown in the output (can be time/computationally intensive)

- For tasks A1, A2 and B1, the output of main.py will show an overall testing accuracy score as a percentage
- For task B2, the output of main.py will show only the individual image prediction scores (the trained model used a sixth 'obscured' class and so is incompatible with input data of five classes)

- For each training script (A1, A2, B1, B2), the path must be changed according to the user's local directory at the beginning of the script

# Requirements

- Pytorch 1.6
- Python 3.7
- numpy 1.14
- seaborn 0.11.0
- Torchvision 0.8.2
- PIL 8.7.1
- Future 0.3.1
- Pandas 1.1.5
