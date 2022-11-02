# Assignment 2: Link Prediction in Graphs

## Colab: https://colab.research.google.com/drive/1WxUZ4IiFVdrOt3-lK_2LyKsnGhju2ppR?usp=sharing

Link prediction is a core graph task by predicting the connection between two nodes based on node attributes. Many real-world tasks can be formed into this problem such as predicting academic article citations for specific topic. Recently, the advancement in graph neural network (GNN) has shifted the link prediction into neural style. Many GNN layers have been able to be applied to the link prediction task directly. But due to some graph structure and graph neural network limitations, the performance of the neural style link prediction sometimes will be negatively influenced. To address these issues, we propose a novel approach to implicitly guide GNN with extracted knowledge. The experiments on a biomedical dataset illustrates the state-of-the-art performance of our method.
