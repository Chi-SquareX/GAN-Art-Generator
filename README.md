# GAN_Art_generator

We used WGANs, CGANS and DCGANs, which leverage the power of the improved wasserstein metric in an extension of the typical AC-GAN framework. Basically this means that we will set up our discriminator and generator under the improved wasserstein model, but in addition we will apply a classification layer to our discriminator where it would also try to predict the genre of a given painting. 

## Dataset:
The model is trained on the publicly available dataset on kaggle. The link to the dataset is as follows: https://www.kaggle.com/thedownhill/art-images-drawings-painting-sculpture-engraving. The proposed experimental scenario the dataset is used for the purpose of classifying different styles of art. Main categories have been taken from the Virtual Russian Museum website, whose link is as follows: https://rusmuseumvrm.ru/collections/index.php?lang=en. The dataset thus compiled and created is downloaded from google images, yandex images and the Virtual Russian Museum website. The data is subdivided into training and validation sets with a number of 7938 and 856 images respectively. The content of each training and validation dataset is divided into 5 categories of art images. The categories are: Drawings and watercolours, Works of painting, Sculpture, Graphic Art, Iconography (old Russian art). The images of the subsequent categories consist of the subfolders named as: drawings, painting, sculpture, engraving, iconography. The diagrammatic representation of the same is shown below. Throughout the paper this dataset is referred to as the “client dataset”.


Another similar publicly available dataset is also used to prove the efficiency of the proposed model, the link to the dataset is as follows: https://www.kaggle.com/ikarus777/best-artworks-of-all-time. It consists of a collection of artworks of the 50 most influential artists of all time with basic information retrieved from Wikipedia. The dataset has a file size of 2GB which is publicly available, hosted on kaggle and can be downloaded easily.  This dataset is referred to as the “other dataset” throughout the course of the paper. The dataset contains three files: artists.csv, images.zip, and resized.zip. The artist.csv contains the information for each artist. It is useful for exploring and knowing in detail about the dataset, depending on where it was extracted from and what distribution of variability it has within the dataset. Lastly the images.zip is a collection of images, wherein all the images are in its full size. The images are divided in subsequent sub-folders and are sequentially numbered.  The resize.zip consists of the same collection of image.zip with the additional feature of the images being resized and all extracted from the sub-folder structure combined in a single folder, named as resized. For our experiment we use the resized.zip and extract the various artistic images. It consists of a total of 8683 images. To train the models this set of images are used as training images to generate art.

## Evaluation metrics:
For evaluation of the generated images, we use visual inspection as well as the more mathematical Frechet Inception Distance (FID). 

FID is a metric used to assess the quality of images created by generative models. It measures the distance between the generated output image and the original input image. The higher value of FID signifies more is the deviation of the generated output from the input image. 

## Experiments:
We experiment with different # of epochs for each model (DCGAN, WGAN, CGAN). In DCGAN, we observe that for the other data, FID decreases with increasing number of epochs, indicating that the model gets better and better as we learn. This intuition is supported by the image quality as well, which gets significantly better as we increase the number of epochs. For # epochs < 100, the images are essentially random blobs without meaning, but by 250 epochs, we observe proper shapes and colors starting to form. It is possible that further increasing the number of epochs will further improve performance, but we are unable to do that with the existing resources available. WGANs are much faster at training and inference, but converge much slower and do not produce very good outputs. 







