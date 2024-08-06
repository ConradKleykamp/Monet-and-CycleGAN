# Monet-and-CycleGAN
Using GANs to Create Monet Style Art (CycleGAN)

![image](https://github.com/user-attachments/assets/8d444ba6-49de-41cb-9956-f822d63fa7ec)

---

### Objective
This project was completed as part of CU Boulder's Introduction to Deep Learning course and as part of Kaggle's "I'm Something of a Painter Myself" competition. The dataset is publicly accessible on Kaggle and contains four directories: monet_tfrec, photo_tfrec, monet_jpg, and photo_jpg. The monet directories contain 300 Monet paintings, each sized as 256x256 pixels. Each Monet directory contains these paintings in either JPEG format or TFRecord format. The photo directories contain 7028 photos, each sized as 256x256 pixels. Each photo is stored as both a JPEG or a TFRecord. The objective of this project is to develop a generative adversarial network (GAN) which will work to convert regular photo images into Monet style paintings. As this is an adversarial model, the generator and the discriminator will work in opposition to eventually create more and more realistic Monet style images. The performance of the GAN will be analyzed via its loss.

---

### Methods
Libraries Used
- matplotlib
- numpy
- seaborn
- tensorflow (keras, layers)

CycleGAN
- Able to do style transfer, which is the main objective of this project
- Able to train without the use of paired data
- Can translate between two domains without having a one-to-one mapping between them 

Building the Generator & Discriminator
- 'monet_generator': transforms photos into Monet style paintings
- 'photo_generator': works backwards, transforms Monet paintings into regular photos
- 'monet_discriminator': determines whether or not an image is a real Monet painting or a generated painting
- 'photo_discriminator': determines whether or not an image is a real photo or a generated photo

Training & Fitting the Model
- 25 epochs
- Metric: Loss
- Adam optimizer

---

### General Results
![image](https://github.com/user-attachments/assets/bcf192c2-7db0-4cb9-b9da-d44e6c6109d8)

CycleGAN Loss
- Monet Generator: 2.6839 (epoch 25)
- Monet Discriminator: 0.6129 (epoch 13)
- Photo Generator: 2.7724 (epoch 25)
- Photo Discriminator: 0.5300 (epoch 3)

From the loss values above, the generator of the CycleGAN model appeared to perform best at the highest number of epochs (25). In contrast, the discriminator tended to perform better at earlier epochs. The photos above show the images produced by the model (Monet Style Output). Here, we can see that the photos have been transformed into a Monet-like image, where the colors and resolutions appear to be softer and blended, thus giving the impression that it is a painting. 
