# Denoising-Medical-Images

Related blog which I have written on denoising images can be found here
https://medium.com/nerd-for-tech/denoising-images-using-autoencoders-4a64499f10ba

## Problem Statement

Due to advancement in technology we might have a large amount of the data but there is always concern about the usability. For example, in medical images like X-rays, MRI, CT scans, Ultrasound, etc., when original images are put in the paper, the quality degrades, due to which the accuracy of the decision model degrades. These images are susceptible to noise.

**Image denoising** is required to suppress noise from noise-contaminated images,and hence, is an important preprocessing step in image analysis. There are many different techniques and methods which can be used for performing denoising such as applying Median, Gaussian, Average, Bilateral Filters, etc. However, they don't necessarily perform well in denoising images without losing much information and hence, an algorithm is needed that can outperform all the other methods that have been proposed.

## Possible Approaches

Traditional approaches for performing denoising include methods like 

1. Gaussian blur: In Gaussian Blur operation, we take a pixel as the average value of its neighboring pixels. The Gaussian filter is a non-uniform low pass filter that removes the high-frequency components and details.
2. Average blur: During this operation, the image is convolved with a box filter. In this process, the central element of the image is replaced by the average of all the pixels in the kernel area.
3. Median blur: The Median blur operation is resembling the other averaging methods. Here, the middle element of the image is replaced by the median of all the pixels in the kernel dimension. This operation processes the edges while extracting out the noise.
4. Bilateral filter: The Bilateral Filter alters the intensity of each and every pixel with a weighted mean of intensity values from neighboring pixels to obtain an edge-preserving and noise-reducing smoothing effect.

To measure the quality of the obtained images using different approaches and compare them with our method, we use what is known as the PSNR (Peak signal-to-noise ratio). It is the ratio between the original noiseless image and the error in the image that is first corrupted and then denoised using the particular algorithm. The higher the PSNR value, the better the quality of the reconstructed image as it has a higher Signal Noise ratio. 

## Methodology-

### Introduction of noise for creating training set-
In order to create the training set, we purposely corrupt the images by adding noise to them stochastically with a random normal distribution having a mean of 0 and standard deviation of 1 with a multiplying factor of 0.07 as the dataset by default contains images without noise. This is done to stimulate the noise which can occur in medical images due to the reasons mentioned in the previous section. The dataset is a compilation of CT scan images meant for studying COVID-19, but we are using it for the purpose of demonstrating denoising.

### Denoising using Autoencoder

Autoencoder is a type of unsupervised learning technique that uses artificial neural networks for the task of representation learning. An autoencoder is made up of two parts-
Encoder- It accepts the input data and maps it to a latent space, which is a compressed form of the data, using deterministic mapping. 
Decoder- It accepts the latent space representation and then maps it back into reconstruction, which has the same shape as the input data using similar mapping.

In other words, the autoencoder seeks to-
Accept input data (corrupted medical images in this case)
It then internally compresses the data into a hidden space representation
Finally, it tries to reconstruct the original data from that hidden representation.


Following is the diagrammatic representation of how the autoencoder works on our images-

![Autoencoder Architecture](https://user-images.githubusercontent.com/42516515/95081968-f92cf180-0737-11eb-92cd-32453c3060bb.png)
