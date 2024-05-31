# MonocularDepth
Computer Vision project that is trained on the KITTI dataset in order to estimate the depth of each pixel given a monocular (single) image

---

Please refer to the Monocular_Depth_n2bajwa.ipynb notebook to see the entire project documentation and explanation. 

## Introduction
Monocular depth estimation is a computer vision task that involves estimating the depth of each pixel given a single 2D (monocular) image. The goal is to derive 3D information from a 2D image.

While many depth-estimation techniques exist like multi-view geometry and stereo reconstruction, machine learning can do better. Learning techniques had been shown to be promising, but most of them utilized fully supervised learning, which relied on having a considerable amount of ground truth depth data at hand.

In 2017, Clément Godard, Oisin Mac Aodha, and Gabriel J. Brostow published a paper titled "Unsupervised Monocular Depth Estimation with Left-Right Consistency" (https://arxiv.org/abs/1609.03677) This paper proposed a new technique for depth estimation which utilized unsupervised or self-supervised learning. It suggests a novel training method (a unique loss function) which allows the CNN to perform depth estimation on a single image, without ground truth data.

This method uses left-right image pairs taken by parallel cameras at a given base-length. It uses the left image to estimate both the left-to-right and right-to-left disparity maps. The left-to-right disparity map is used to reconstruct the right image, and the right-to-left disparity map is used to reconstruct the left image. The reconstructed images are then compared with the original images, and used to drive the loss function.

I will be attempting to follow this same method while implementing unsupervised/self-supervised monocular depth estimation.

<img width="725" alt="Screen Shot 2024-05-31 at 4 11 31 PM" src="https://github.com/NimunB/MonocularDepth/assets/32827637/74f04d04-2c91-4437-8536-3d7449c02587">
