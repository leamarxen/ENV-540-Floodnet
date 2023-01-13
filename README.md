# Repository details

The repository contains the following files/folders :

   - data : contains a few images from the test set (the ones used in the report)
   - Evaluation.ipynb : predicts classes on the test dataset; the trained model is loaded
   - floodnet.ipynb : trains the model and get performances scores for training and validation datasets
   - FloodNet_split_train_valid_test.csv : contains the name of all images with their classification in train, validation or test set
   - model_param.pth : contains all information about the trained model (this file is produced by floodnet.ipynb)
   - readme.md
   - resnet101.pth : contains the weights of the Resnet model




# Instructions to run Evaluation.ipynb

## download the trained model parameters here : https://drive.google.com/file/d/18zRjxfEl7Ipsswb4UnvnMeCPnAoeDoAI/view?usp=sharing

# create a local virtual environment in the venv folder
>>>> python -m venv venv
# increase the memory of CUDA by setting the parameter of the following environment variable (to be able to load the trained model)
> set 'PYTORCH_CUDA_ALLOC_CONF=max_split_size_mb:512'
# activate this environment
> source venv/bin/activate
# run with 
> jupyter notebook

Further information : 

   - The simulation should last less than a few minutes with 64 GB RAM.




# Instructions to run floodnet.ipynb

To run the code, you need all images. For this, download the folder data from https://drive.google.com/drive/folders/1jOyH0aNXcN5F2uLGyGyAoWUbT8EWYZFd?usp=sharing. Then, 

# create a local virtual environment in the venv folder
>>>> python -m venv venv
# activate this environment
>>>> source venv/bin/activate
# run with 
>>>> jupyter notebook

Further information : 

   - This simulation should last around one hour and a half with 2 gpus and 64 GB RAM.
   - In this run, to save computation time, the mean and standard deviation of the pixel values over all images are not recomputed (they were computed once and are now hardcoded since these information don't change over simulations). To compute them, set RECOMPUTE_MEAN_STD to True in the third code cell.
