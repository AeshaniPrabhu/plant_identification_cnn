# Plant Identification using CNN
##### Farmers need to differentiate between various plants and the weeds in a field. This process is not always easy, rather it requires a lot of time and effort. It is a very crucial task to identify these weeds in a timely manner, since they use up some part of the nutrients provided for the crop. Early identification of the weed can lead to a better yield and a good crop quality. In the long run it can help in better care for the environment. Hence, we have proposed a CNN model that will identify plants from their images and classify into categories. Using this model, we can automate the identification process and as a result a lot of time and effort is saved. 

## Getting Started
##### First you will need to download the dataset from the following link: https://www.kaggle.com/c/plant-seedlings-classification. Then after unzipping the dataset, place it in your working directory in your Google Drive. Then mount your google drive onto Google Colab Notebook. For running the project, you need to execute the "plant_identification.ipynb" file in a Google Colab notebook. 

## Installations
##### You will need to install the following python libraries:
##### 1. numpy
##### 2. pandas
##### 3. cv2
##### 4. seaborn
##### 5. matplotlib

## Dataset
##### We have used a dataset called plant-seedlings-classification from Kaggle. The dataset has approximately 4764 images, which are categorized into 12 classes i.e. there are 12 different plant species. All the images are in the RGB (Red Green Blue) format. The plants in the images are at various stages of growth. 

## Data Pre-processing
##### As we explored the dataset, we realized that all the images are not of the same size. Therefore, using data augmentation we resized all the images to 256 x 256. Then we converted the RBG format of the images to HSV (Hue Saturation Value). Then we carried out segmentation on the images, which is the process of partitioning an image into multiple segments, to locate objects and boundaries effectively. Lastly, we performed sharpening of the images, to increase the contrast between light and dark regions of the image, to highlight the features. In this manner, using various techniques, we made the available data fit for use.

## The CNN Model
##### First, we split the entire dataset into 70% training set and 30% testing set. Then we further split the 70% training set into 50% training set and 50% testing set. Then we designed a CNN model having 6 convolution layers. These layers have filters ranging from 32 up to 128. We have given the first 2 layers a kernel size of 5 x 5 and that of other layers is 3 x 3. We have used the padding size as “same”, since we wanted to preserve the dimensions of the data. Then all of the layers have a ReLU activation function, which is linear for all positive values and zero for all negative values. We have also added max pool layers, of pool size 2 x 2 and stride 2 x 2. To avoid overfitting of the model we a dropout of 0.2. Finally, we have added fully connected layers or dense layers. The classification layer has the Softmax activation function, since it is a multiclass classification, which represents the input as a probability distribution.
