# Assignment 5

## Active learning with label studio

This combines Lightly and LabelStudio for showing a complete workflow of creating a machine learning model including Active Learning.

1. It starts with collecting unlabelled data.
2. Then it uses Lightly to choose a subset of the unlabelled to be labelled.
3. This subset is labelled with the help of LabelStudio.
4. A machine learning model is trained on the labeled data and Active Learning is used to choose the next batch to be labelled.
5. This batch is labelled again in LabelStudio.
6. The machine learning model is trained on the updated labelled dataset.
7. Finally, the model is used to predict on completely new data.
