# Assignment 5

## Active learning with lightly.ai

Active learning is a process of using model predictions to find a new set of images to annotate. The images are chosen to have a maximal impact on the model performance. In this tutorial, we will use a pre-trained object detection model to do active learning on a completely unlabeled set of images.
In machine learning, we often don't train a model from scratch. Instead, we start with an already pre-trained model. For object detection tasks, a common pre-training dataset is MS COCO consisting of over 100'000 images containing 80 different classes. Our goal is to take an MS COCO pre-trained model and optimize it for an autonomous driving task. We will proceed as follows: First, we will use the pre-trained model to make predictions on our task dataset (Comma10k) which has been collected for autonomous driving. Then, we use the predictions, self-supervised learning, and active learning with the lightly framework to find the 100 most informative images on which we can finetune our model.
The assignment is divided into the following steps.
Installation of detectron2 and lightly.
Run predictions using a pre-trained model.
Use lightly to compute active learning scores for the predictions.
Use the Lightly Platform to understand where our model struggles.
Select the most valuable 100 images for annotation.
Requirements
Make sure you have OpenCV installed to read and preprocess the images. You can install the framework using the following command: pip install opencv-python
Make sure you have the detectron2 framework installed on your machine. Check out the detectron2 installation documentation <https://detectron2.readthedocs.io/en/latest/tutorials/install.html>_

To work with the Lightly Platform and use the active learning feature we need to upload the dataset.
First, head over to the Lightly Platform <https://app.lightly.ai/>_ and create a new dataset.
We can now upload the data using the command line interface. Replace yourToken and yourDatasetId with the two provided values from the web app. Don't forget to adjust the input_dir to the location of your dataset.
.. code::
lightly-magic token="yourToken" dataset_id="yourDatasetId" \
    input_dir='/datasets/comma10k/imgs/' trainer.max_epochs=20 \
    loader.batch_size=64 loader.num_workers=8
Note

In this tutorial, we use the lightly-magic command which trains a model before embedding and uploading it to the Lightly Platform. To skip training, you can set `trainer.max_epochs=0`.
  lightly-magic   
  token='5107ca368424f355f0068e0d0dfe1c2f91e417c822e8a528' 
  dataset_id='637420e0496cb15dd6af31a5' 
  input_dir='path_to_your_dataset' 
  trainer.max_epochs=20
  
  Finally, we can tell our agent to select the top 100 images to annotate and improve our existing model. We pick the selection strategy called CORAL which is a combination of CORESET and Active Learning. Whereas CORESET maximizes the image diversity based on the embeddings, active learning aims at selecting images where our model struggles the most.
