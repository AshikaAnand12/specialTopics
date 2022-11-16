# Assignment 5
Continual learning using Avalanche library

In this notebook we will talk about the features offered by the models Avalanche sub-module.

Support for pytorch Modules

Every continual learning experiment needs a model to train incrementally. You can use any torch.nn.Module, even pretrained models. The models sub-module provides for you the most commonly used architectures in the CL literature.

You can use any model provided in the Pytorch official ecosystem models as well as the ones provided by pytorchcv!

A continual learning model may change over time. As an example, a classifier may add new units for previously unseen classes, while progressive networks add a new set units after each experience. Avalanche provides DynamicModules to support these use cases. DynamicModules are torch.nn.Modules that provide an addition method, adaptation, that is used to update the model's architecture. The method takes a single argument, the data from the current experience.


