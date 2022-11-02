# Assignment 2: Node Classification
## Colab : https://colab.research.google.com/drive/1PFAlOIoh19Q4f9u-e--yYBuJs0jc1RFY?usp=sharing

1. We aim to train a graph-ML model that will predict the "subject" attribute on the nodes. These subjects are one of 7 categories, with some categories more common than others.
2. For machine learning we want to take a subset of the nodes for training, and use the rest for validation and testing. We'll use scikit-learn's train_test_split function.
3. Here we're taking 140 node labels for training, 500 for validation, and the rest for testing.
4. To create a Keras model we now expose the input and output tensors of the GCN model for node prediction, via the GCN.in_out_tensors method.
5. As the final part of our evaluation, let's check the model against the test set. We again create the data required for this using the flow method on our FullBatchNodeGenerator from above, and can use the model's evaluate method to compute the metric values for the trained model.
6. As expected, the model performs similarly on the validation set during training and on the test set here.
7. These predictions will be the output of the softmax layer, so to get final categories we'll use the inverse_transform method of our target attribute specification to turn these values back to the original categories.
