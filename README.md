# GAN_Art_generator

We used WGANs, CGANS and DCGANs, which leverage the power of the improved wasserstein metric in an extension of the typical AC-GAN framework. Basically this means that we will set up our discriminator and generator under the improved wasserstein model, but in addition we will apply a classification layer to our discriminator where it would also try to predict the genre of a given painting. 

## Model Architecture:
Generator:

<img width= 350, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/generator.png" alt="Generator" />

Discriminator:

<img width= 350, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/discriminator.png" alt="Discriminator" />

## Dataset:
The model is trained on the publicly available dataset on kaggle. The link to the dataset is as follows: https://www.kaggle.com/thedownhill/art-images-drawings-painting-sculpture-engraving. The proposed experimental scenario the dataset is used for the purpose of classifying different styles of art. The content of each training and validation dataset is divided into 5 categories of art images. Throughout the paper this dataset is referred to as the “client dataset”. 

<img width= 50, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/data.png" alt="Data Format" />

Another similar publicly available dataset is also used to prove the efficiency of the proposed model, the link to the dataset is as follows: https://www.kaggle.com/ikarus777/best-artworks-of-all-time. It consists of a collection of artworks of the 50 most influential artists of all time with basic information retrieved from Wikipedia. The resize.zip consists of the same collection of image.zip with the additional feature of the images being resized and all extracted from the sub-folder structure combined in a single folder, named as resized. 

## Evaluation metrics:
For evaluation of the generated images, we use visual inspection as well as the more mathematical Frechet Inception Distance (FID). 

FID is a metric used to assess the quality of images created by generative models. It measures the distance between the generated output image and the original input image. The higher value of FID signifies more is the deviation of the generated output from the input image. 

## Results: 
<img width= 300, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/Clientdataset.png" alt="Results Client Dataset" /><img width= 300, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/Otherdataset.png" alt="Results Other Dataset" />

## Experiments:
We experiment with different # of epochs for each model (DCGAN, WGAN, CGAN). In DCGAN, we observe that for the other data, FID decreases with increasing number of epochs, indicating that the model gets better and better as we learn. This intuition is supported by the image quality as well, which gets significantly better as we increase the number of epochs. For # epochs < 100, the images are essentially random blobs without meaning, but by 250 epochs, we observe proper shapes and colors starting to form. It is possible that further increasing the number of epochs will further improve performance, but we are unable to do that with the existing resources available. WGANs are much faster at training and inference, but converge much slower and do not produce very good outputs. 

<img width= 450, src="https://github.com/Chi-SquareX/GAN-Art-Generator/blob/f9f15ba34e09282dbcefbaf0ead7ddc730afc53c/Figures/results.png" alt="Results" />
