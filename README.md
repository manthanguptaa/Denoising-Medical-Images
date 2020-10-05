# Denoising-Medical-Images

## Problem Statement

Due to advancement in technology we might have a large amount of the data but there is always concern about the usability. For example in images like X-rays , MRI, CT scans, Ultrasound, etc., when original images are put in the paper, the quality degrades, due to which the accuracy of the decision model degrades. These images are susceptible to noise.

**Image denoising** is required to suppress noise from noise-contaminated images,and hence, is an important preprocessing step in image analysis. There are many different techniques and methods which can be used for performing denoising such as applying Median, Gaussian, Average, Bilateral Filters, etc. However, they don't necessarily perform well in denoising of images without loosing much information and hence, an algorithm is needed that can outperform all the other methods that have been proposed.

## Methodology-

### Introduction of noise for creating training set-
In order to create the training set, we purposely corrupt the images by adding noise to them stochastically with a random normal distribution having a mean of 0 and standard deviation of 1 with a multiplying factor of 0.07 as the dataset by default contains images without noise. This is done to stimulate the noise which can occur in medical images due to the reasons mentioned in the previous section. The dataset is a compilation of CT scan images meant for studying COVID-19, but we are using it for the purpose of demonstrating denoising.


Following is the diagrammatic representation of how the autoencoder works on our images-

![Autoencoder Architecture](https://user-images.githubusercontent.com/42516515/95081968-f92cf180-0737-11eb-92cd-32453c3060bb.png)
