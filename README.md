# Assignment 4
Colab: https://drive.google.com/file/d/19jMkJnptJg4pUQ8jK8Iv2K7Osp0st1UU/view?usp=sharing

 This class will facilitate the creation of a few-shot dataset from the Omniglot dataset that can be sampled from quickly while also allowing to create new labels at the same time. Iterate over the dataset to get each individual image and its class, and put that data into a dictionary. Perform SGD for the meta step. After the meta-learning step, reload the newly-trained weights into the model. First, some preprocessing to smooth the training and testing arrays for display. Display the training accuracies.
