AIM :
Food-101 is a challenging vision problem, but everyone can relate to it.  Recent SoTA is ~80% top-1, 90% top-5.  These approaches rely on lots of TTA, large networks and  even novel architectures.

Train a decent model >85% accuracy for top-1 for the test set, using a ResNet50 or smaller network with a reasonable set of augmentations.   


A Dataset for Learning to Address Label Noise

The Food-101N dataset is introduced in a CVPR 2018 paper CleanNet: Transfer Learning for Scalable Image Classifier Training with Label Noise from Microsoft AI & Research. The dataset is designed for learning to address label noise with minimum human supervision.

Food-101N is an image dataset containing about 310,009 images of food recipes classified in 101 classes (categories). Food-101N and the Food-101 dataset share the same 101 classes, whereas Food-101N has much more images and is more noisy.

In this dataset, we define two types of labels for images:

Class labels: a class label describes the class of an image. Class labels are noisy, which means they could be incorrect. Each image in this dataset has a class label. The estimated noise rate is ~20%.

Verification labels: a verification label marks whether the class label is correct for an image. We manually assign verification labels to 52,868 images (~523 images per class) for training and 4,741 images (~47 images per class) for validation.

In our paper CleanNet: Transfer Learning for Scalable Image Classifier Training with Label Noise, we explored using transfer learning to address label noise. Specifically for some experiments, we only keep verification labels for part of the classes so that we only learn from human supervision for some of the classes and transfer the knowledge to address label noise in other classes. For future research to follow the experiments in the paper, we also include the held-out class lists in this dataset.

Tasks and Evaluation

Food-101N is designed for the following two tasks:

Learning image classification with label noise
Food-101N directly adopts the testing set of Food-101 to evaluate image classification.

Here we provide an image classification baseline using ResNet-50 without any human verification:

Dataset	Top-1 Accuracy
Food-101N	81.44%
Food-101	81.67%
The above results also show that Food-101N perform comparably to Food-101. Please refer to the paper for more results.

Label noise detection
Food-101N provides 4,741 images with verification labels for validation.
