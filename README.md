# Assignment 5
Continual learning using Avalanche library

In this notebook we will talk about the features offered by the models Avalanche sub-module.

Support for pytorch Modules

Every continual learning experiment needs a model to train incrementally. You can use any torch.nn.Module, even pretrained models. The models sub-module provides for you the most commonly used architectures in the CL literature.

You can use any model provided in the Pytorch official ecosystem models as well as the ones provided by pytorchcv!

A continual learning model may change over time. As an example, a classifier may add new units for previously unseen classes, while progressive networks add a new set units after each experience. Avalanche provides DynamicModules to support these use cases. DynamicModules are torch.nn.Modules that provide an addition method, adaptation, that is used to update the model's architecture. The method takes a single argument, the data from the current experience.

Some models, such as multi-head classifiers, are designed to exploit task labels. In Avalanche, such models are implemented as MultiTaskModules. These are dynamic models (since they need to be updated whenever they encounter a new task) that have an additional task_labels argument in their forward method. task_labels is a tensor with a task id for each sample.

When you use a MultiHeadClassifier, a new head is initialized whenever a new task is encountered. Avalanche strategies automatically recognizes multi-task modules and provide the task labels to them.

How to define a multi-task Module

If you want to define a custom multi-task module you need to override two methods: adaptation (if needed), and forward_single_task. The forward method of the base class will split the mini-batch by task-id and provide single task mini-batches to forward_single_task.
