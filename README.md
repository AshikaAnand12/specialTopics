# Assignment 4
Colab: https://drive.google.com/file/d/1kZBrLz7OdJbM8m8C_mK9mWlQerSY1XzP/view?usp=sharing

We implement Meta-BERT that trains BERT for fast adapting to new tasks using limited examples. The distinctive feature of Meta-BERT is to meta-train the BERT model using First-Order-MAML, FOMAML, which enables the model to learn new tasks quickly.

The proposed algorithm is a model-agnostic, in the sense that it can be directly applied to any BERT architecture. We investigate the capacity to adapt Meta-BERT and BERT models to the unseen tasks in which only a limited set of task-specific data are available. We demonstrate that our Meta-BERT outperforms BERT in low-resource fine-tuning by +2.2% accuracy improvement. For zero-shot classification, Meta-BERT achieves +5.7% improvement compared to BERT model.
