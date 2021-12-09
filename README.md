# Pollen-Data-Classification-using-Vision-Transformer

In this project, we have decided to explore the current state of the art vision transformer for testing pollen grain image classification problem from ICPR 2020. 
We have decided to work on this topic because we believe this work will be noble for this challenge and will also help us get a deeper understanding of the multi head self attention mechanism for vision tasks. 
The CNN only classifiers do not take into account the global information of the image however the transformer takes the global information about the image into account which helps to make the decision making of the system more robust.

The folders are arranged on following manner:

Each ViT16 and ViT32 folders contains the following folders which are designed in following manner:

1. Version 1 --> Only the classification head is trained --> 4K Parameters 
2. Version 2 --> Classification head and 11th block are trained --> 7M Parameters
3. Version 3 --> Classification head, (10, 11) blocks are trained --> 14M Parameters
4. Version 4 --> Classification head, (9, 10, 11) blocks are trained --> 21M Parameters
5. Version 5 --> Classification head, (8, 9, 10, 11) blocks are trained --> 28M Parameters
6. Version 6 --> Classification head, (7, 8, 9, 10, 11) blocks are trained --> 35M Parameters


Several experiments were performed, providing below results.
Performance of different models trained for 10 epochs, and the performance plateau were obtained for all the models. The best performance of the different models are summarized below. Score here reported are only accurac. Other F1-weighted and F1-Macro scores can be found in the notebooks.
|        Model       |      Model Part trained         | Validation Score |
|:------------------:|:-------------------------------:|:----------------:|
|====================|==========Adam Optimizer=========|==================|
|ViT16               |   Head only                     |     92.4%        |
|ViT16               |   Head + 11th block             |     94.2%        |
|ViT16               |   Head + (11,10)  block         |     94.5%        |
|ViT16               |   Head + (11,10,9)  block       |     94.5%        |
|ViT16               |   Head + (11,10,9,8)  block     |     94.6%        |
|ViT16               |   Head + (11,10,9,8,7)  block   |     94.9%        |
|--------------------|---------------------------------|------------------|
|ViT32               |   Head only                     |     92.3%        |
|ViT32               |   Head + 11th block             |     94.5%        |
|ViT32               |   Head + (11,10)  block         |     94.1%        |
|ViT32               |   Head + (11,10,9)  block       |     94.5%        |
|ViT32               |   Head + (11,10,9,8)  block     |     94.9%        |
|ViT32               |   Head + (11,10,9,8,7)  block   |     94.5%        |
|====================|=======AdaBelief Optimizer=======|==================|
|ViT16               |   Head only                     |     92.7%        |
|ViT16               |   Head + 11th block             |     94.5%        |
|ViT16               |   Head + (11,10)  block         |     95.0%        |
|ViT16               |   Head + (11,10,9)  block       |     95.1%        |
|ViT16               |   Head + (11,10,9,8)  block     |     94.7%        |
|ViT16               |   Head + (11,10,9,8,7)  block   |     95.2%        |
|--------------------|---------------------------------|------------------|
|ViT32               |   Head only                     |     91.9%        |
|ViT32               |   Head + 11th block             |     94.5%        |
|ViT32               |   Head + (11,10)  block         |     94.6%        |
|ViT32               |   Head + (11,10,9)  block       |     95.2%        |
|ViT32               |   Head + (11,10,9,8)  block     |     95.1%        |
|__ViT32__           |   Head + (11,10,9,8,7)  block   |   __95.6%__      |
|ViT32               |   Head + (11,10,9,8,7,6)  block |     94.6%        |

Best trained model and latest checkpoints can be found in this [link](https://kuacae-my.sharepoint.com/:f:/g/personal/100058927_ku_ac_ae/ElAIxKpwEE1FtXSUAY435A4B7EIXLa7ouQMnJ-uwcJ5uWw?e=6mKEjd)

### Best Ensembled Model Performance on Validation and Test Set

More detail on model selected for ensembling and testing is in this [notebook](notebooks/https://github.com/ghimireadarsh/Pollen-Data-Classification-using-Vision-Transformer/blob/master/Notebooks/3%20Final%20Model%20Validation%2C%20Ensembling%20and%20Testing.ipynb)

Models selected :
1. Model 1 - ViT16, Version 4
2. Model 2 - ViT16, Version 6
3. Model 3 - ViT32, Version 5
4. Model 4 - ViT32, Version 6

Only the best model combination and the correponding test results are reported
|        Model Combination       |      Validation Score         | Test Score |
|:------------------------------:|:-----------------------------:|:----------:|
|            1, 4                |        96.3652%               |  94.5922%  |
|            1, 3, 4             |        96.4539%               |  94.8582%  |
|            1, 2, 3, 4          |        96.4539%               |  94.9468%  |

