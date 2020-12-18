# README
# AMLS_2020-2021_20164490
This code contains the scripts to train four models for differernt image recognition tasks. Tasks A1 and A2 involve determining the gender and smiling status of real celebrity images, and B1 and B2 aim to determine the face shape and eye colour of cartoon avatar aimages. Trained models are intended to be saved in the folder for each task to allow main.py to run.

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
          max_epochs_stop=5,
          n_epochs=20,
          print_every=1,
          ):
    - begins trains model with model.train
    - prints training and validation accuracy and loss
    - updates weights for next repetition
    - iterates through specified number of epochs


# Use on command line

- X
    
    - A1 Model download folder, requires saving in A1 folder
    https://drive.google.com/file/d/1-3AU2etnp2I5Fr9D_eicAC_pd1a8G8IH/view?usp=sharing
    
