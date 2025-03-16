# NEURAL-STYLE-TRANSFER

COMPANY: CODTECH IT SOLUTIONS

NAME: KONDAMADUGU RAHUL CHARY

INTERN ID: CT12ONT

DOMAIN: ARTIFICIAL INTELLIGENCE

DURATION: 4 WEEKS

MENTOR: NEELA SANTOSH

Description:-

Neural Style Transfer is the ability to create a new image (known as a pastiche) based on two input images: one representing the content and the other representing the artistic style.

This repository contains a lightweight PyTorch implementation of art style transfer discussed in the seminal paper by Gatys et al. To make the model faster and more accurate, a pre-trained VGG19 model is used.

🔗Check out this article by me regarding the same.
Table of Contents
Overview
How does it work?
File Description
Getting Started
Dependencies
Usage
Output
Acknowledgements
License
Star History
Overview
Neural style transfer is a technique that is used to take two images—a content image and a style reference image—and blend them together so that output image looks like the content image, but “painted” in the style of the style reference image.

How does it work?
We take content and style images as input and pre-process them.

Next, we load VGG19 which is a pre-trained CNN (convolutional neural network).

Starting from the network's input layer, the first few layer activations represent low-level features like colors, and textures. As we step through the network, the final few layers represent higher-level features—like eyes.
In this case, we use conv1_1, conv2_1, conv3_1, conv4_1, conv5_1 for style representation, and conv4_2 for content representation.

We begin by cloning the content image and then iteratively changing its style. Then, we set our task as an optimization problem where we try to minimize:

content loss, which is the L2 distance between the content and the generated image,
style loss, which is the sum of L2 distances between the Gram matrices of the representations of the content image and the style image, extracted from different layers of VGG19.
total variation loss, which is used for spatial continuity between the pixels of the generated image, thereby denoising it and giving it visual coherence.
Finally, we set our gradients and optimize using the L-BFGS algorithm to get the desired output.

Getting Started
File Description
Neural-Style-Transfer
    ├── data
    |   ├── content-images
    |   ├── style-images
    ├── models/definitions     
    │   ├── vgg19.py   <-- VGG19 model definition
    ├── NST.py  <-- the main python file
    ├── LICENSE
    └── README.md
Dependencies
Python 3.9+
Framework: PyTorch
Libraries: os, numpy, cv2, matplotlib, torchvision
Usage
    $ pip install -r requirements.txt
To implement Neural Style Transfer on images of your own:
Clone the repository and move to the downloaded folder:
    $  git clone https://github.com/nazianafis/Neural-Style-Transfer
    $  cd Neural-Style-Transfer
Move your content/style image(s) to their respective folders inside the data folder.

Go to NST.py, and in it, set the PATH variable to your downloaded folder. Also set CONTENT_IMAGE, STYLE_IMAGE variables as your desired images:

    $ PATH = <your_path>
   
    $ CONTENT_IMAGE = <your_content_image_name>
    $ STYLE_IMAGE = <you_style_image_name>
Run NST.py:
    $ python NST.py
Find your generated image in the output-images folder inside data.
Output
The following images were generated using no image manipulation program(s) other than the code described in this article.

content

Acknowledgements
These are some of the resources I referred to while working on this project. You might want to check them out.

PyTorch's tutorial on NST.
Aleksa Gordic's implementation.
The original paper on neural style transfer by Gatys et al .
The original paper on VGG19.
Wikimedia, Unsplash for all the content and style images.
License
License: MIT

#OUTPUT:

