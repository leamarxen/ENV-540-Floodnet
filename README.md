# Repository details

The repository contains the following files/folders :

   - data : contains a few images from the test set (to run Evaluation.ipynb)
   - Evaluation.ipynb : predicts classes on the test dataset; the trained model is loaded
   - floodnet.ipynb : trains the model and gets performances scores for training and validation datasets
   - FloodNet_split_train_valid_test.csv : contains the name of all images with their classification in train, validation or test set
   - readme.md




# Instructions to run Evaluation.ipynb

To run the code, you need the parameters of the trained model, to be downloaded here : https://drive.google.com/file/d/18zRjxfEl7Ipsswb4UnvnMeCPnAoeDoAI/view?usp=sharing. The downloaded file is named 'model_param.pth', it was produced by 'floodnet.ipynb'.

For the test images, either you download the folder 'data' from https://drive.google.com/drive/folders/1jOyH0aNXcN5F2uLGyGyAoWUbT8EWYZFd?usp=sharing to have the 60 test images (around 2GB), either you use only a few of them, already given in the folder 'data' from this repository. If you choose the first option, you need to set 'all_images' to 'True' in the first code cell of 'Evaluation.ipynb'. Otherwise, set it to 'False'. 

To run:
```
# create a local virtual environment in the venv folder
python -m venv venv
# increase the memory of CUDA by setting the parameter of the following environment variable (to be able to load the trained model)
set 'PYTORCH_CUDA_ALLOC_CONF=max_split_size_mb:512'
# activate this environment
source venv/bin/activate
# run with 
jupyter notebook
```
The necessary dependencies are installed within the jupyter notebook.

Further information : 

   - The simulation with only a few images should last less than a few minutes with 64 GB RAM.




# Instructions to run floodnet.ipynb

To run the code, you need all images. For this, download the folder 'data' from https://drive.google.com/drive/folders/1jOyH0aNXcN5F2uLGyGyAoWUbT8EWYZFd?usp=sharing. Then, 
You also need the parameters for the pre-trained Resnet model, found here : https://download.pytorch.org/models/resnet101-5d3b4d8f.pth. Then rename the file as 'resnet101.pth'.

To run:
```
# create a local virtual environment in the venv folder
python -m venv venv
# activate this environment
source venv/bin/activate
# run with 
jupyter notebook
```
The necessary dependencies are installed within the jupyter notebook.

Further information : 

   - This simulation should last around one hour and a half with 2 gpus and 64 GB RAM.
   - In this run, to save computation time, the mean and standard deviation of the pixel values over all images are not recomputed (they were computed once and are now hardcoded since these information don't change over simulations). To compute them, set 'RECOMPUTE_MEAN_STD' to 'True' in the third code cell.
