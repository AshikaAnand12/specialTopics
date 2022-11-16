# Assignment 5

## Active learning with label studio

This tutorial combines Lightly and LabelStudio for showing a complete workflow of creating a machine learning model including Active Learning.

It starts with collecting unlabelled data.
Then it uses Lightly to choose a subset of the unlabelled to be labelled.
This subset is labelled with the help of LabelStudio.
A machine learning model is trained on the labeled data and Active Learning is used to choose the next batch to be labelled.
This batch is labelled again in LabelStudio.
The machine learning model is trained on the updated labelled dataset.
Finally, the model is used to predict on completely new data.
