# [Medium Draft Link](https://medium.com/@sukantkumar_56181/distributed-machine-learning-architectures-733776a85222)

# Distributed Machine Learning Architectures
Progress in Modern day machine learning is spearheaded by 2 factors considerably:
- Explosion in amount of data available for training
- Increasigly complex model architectures with billions (or trillions) of parameters

In this scenario, its pretty common for you to come across a situation where any of the following things can happen:
- Your data doesn't fit in memory of a single machine
- The model itself has become too big to be loaded into RAM
- Even if the model and data could be loaded into memory, the model training process would be painfully slow

Let me illustrate the point with some examples.
Suppose you are working on an image classification problem. You are using CIFAR-10 and CIFAR-100 datasets for training your model.
In CIFAR-10/100 the image resolution of each image is 32X32. So the image sizes(quality) are pretty small.
If you try to train a VGG-19 or ResNet-50 model using a single machine with GPU available, it will take a <b>few hours</b> but still the task will be done.

Now suppose you want to use higher quality images and use ImageNet-1K dataset. The images in this dataset have a higher resolution (256X256).
If you start training the same VGG-19 or ResNet-50 model on this dataset using single GPU machine that you'd used earlier,
Now you'll be waiting for days. The expected time would be in the range of <b>10-14 days (1-2 weeks)</b>. 
This would be a non-starter if you want to train your own deep learning models with complex structures. 
And a point to ponder over is that -  ImageNet-1K is not a new dataset as well as ResNet-50 is not some recent model with very complex architecture 
compared to recent developments in ML models that we have seen (say LLMs).

