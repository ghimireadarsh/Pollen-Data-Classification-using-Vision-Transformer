# Pollen-Data-Classification-using-Vision-Transformer

In this project, we have decided to explore the current state of the art vision transformer for testing pollen grain image classification problem from ICPR 2020. 
We have decided to work on this topic because we believe this work will be noble for this challenge and will also help us get a deeper understanding of the multi head self attention mechanism for vision tasks which we believe is quite necessary. 
The CNN only classifiers do not take into account the global information of the image however the transformer takes the global information about the image into account which helps to make the decision making of the system more robust.

The folders are arranged on following manner:

Each ViT16 and ViT32 folders contains the following folders which are designed in following manner:

1. Version 1 --> Only the classification head is trained --> 4K Parameters 
2. Version 2 --> Classification head and 11th block are trained --> 7M Parameters
3. Version 3 --> Classification head, 10th and 11th blocks are trained --> 14M Parameters

Performance of different models trained for 5 epochs
|        Model       |      Model Part trained       |  Validation Score|
|:------------------:|:-----------------------------:|:----------------:|
|ViT16               |             Head only         |     91.9%        |
|ViT16               |           Head + 11th block   |     93.1%        |
|ViT16               |   Head + 11th + 10th  block   |     94.2%        |
|ViT32               |   Head only                   |     91.8%        |
|ViT32               |   Head + 11th block           |     93.8%        |
|ViT32               |   Head + 11th + 10th  block   |     94.3%        |
